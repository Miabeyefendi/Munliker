# 📘 Munliker: Detaylı Yapılandırma ve Özelleştirme Rehberi

> **[EN] Click [here](tutorial.md) for the English version of this guide.**
> *Bu rehberin İngilizce versiyonuna yukarıdaki bağlantıdan ulaşabilirsiniz.*

**Munliker** teknik derinlemesine inceleme rehberine hoş geldiniz. Bu döküman; botun mimarisini, hangi dosyanın ne işe yaradığını ve botun davranışını, hızını ve gizlilik seviyesini değiştirmek için hangi satırları modifiye etmeniz gerektiğini açıklar.

---

## 🏗️ Proje Mimarisine Genel Bakış

Munliker modüler bir yapıda inşa edilmiştir. Görevler uzmanlaşmış yöneticiler arasında bölünmüştür:
- **Ana Mantık:** `config.py` ve `main.py`
- **Davranış Simülasyonu:** `human_actions.py`
- **Yürütme (Execution):** `unlike_manager.py`
- **Oturum ve Yetkilendirme:** `session_manager.py` ve `instagram_auth.py`
- **Tanılama Araçları:** `debug.py`, `finder.py`, `detector.py`

---

## ⚙️ 1. `config.py` — Ana Beyin

Bu dosya kullanıcılar için en önemli dosyadır. Botu kontrol eden hemen hemen her sayısal değer burada bulunur.

### 🕒 Unlike Hızı ve Limitler
- **`MAX_UNLIKE_PER_HOUR`**: Varsayılan olarak `44` ayarlanmıştır.
  - *Modifikasyon:* Eğer hesabınız eskiyse (5+ yıl), bunu `50-60` seviyesine çıkarabilirsiniz. Yeni bir hesapsa `20` seviyesine düşürün.
- **`UNLIKE_DELAY`**: `(7, 45)` saniye.
  - *Modifikasyon:* İki beğeni kaldırma arasındaki rastgele bekleme süresidir. Ultra güvenli olmak için `(30, 90)` olarak değiştirebilirsiniz.
- **`UNLIKE_FIRST_BATCH` ve `SECOND_BATCH`**:
  - *Mantık:* Bot birkaç postun beğenisini kaldırır, sonra Reels/DM izlemeye gider, sonra tekrar döner. Bu değerler her "turda" kaç post silineceğini belirler.

### 📱 Cihaz Simülasyonu (Samsung Galaxy S24 Ultra)
- **`VIEWPORT`**: `{"width": 412, "height": 915}`. S24 Ultra ekran oranına tam uyumludur.
- **`USER_AGENT`**: Instagram'a Android 14 üzerinde güncel bir Chrome kullandığınızı bildiren özel kimlik bilgisidir.
- **`DEVICE_PROFILE`**: Dil (`tr_TR`) ve zaman dilimi bilgilerini içerir.
  - *Özelleştirme:* Eğer botu Türkiye dışından kullanıyorsanız, "Şüpheli Giriş" uyarısı almamak için `locale` ve `timezone` değerlerini bulunduğunuz bölgeye göre güncelleyin.

---

## 🎭 2. `human_actions.py` — Gizlilik Motoru

Bu dosya "Dolgu Eylemleri" içerir. Eğer bot sadece beğeni kaldırsaydı, Instagram yapay zekası bunu anında fark ederdi. Bu script botun "canı sıkılmış bir insan" gibi görünmesini sağlar.

- **`REELS_VIEW_TIME_LONG`**: `(14, 35)` saniye.
  - *Mantık:* Bot bazen Reels videolarını sadece geçmek yerine sonuna kadar izler.
- **`REELS_LONG_CHANCE`**: `0.3` (%30 ihtimal).
  - *Modifikasyon:* Bunu `0.5` yaparak botun Reels'ta daha fazla kalmasını sağlayabilir, "Hesap Isınma" (Account Warmth) oranını artırabilirsiniz.
- **`browse_home()`**: Akışı yeniler ve rastgele kaydırır. Arkadaşlarınızdan gelen yeni gönderileri kontrol ediyormuşsunuz gibi davranır.

---

## 🧹 3. `unlike_manager.py` — Uygulayıcı

Gerçek tıklama işlemlerinin yapıldığı yerdir. "Beğenilen Gönderiler" sayfasına navigasyonu ve "Beğenmekten Vazgeç" butonunu bulma mantığını yönetir.

### 🔍 Grid (Izgara) Navigasyon Sistemi
Instagram'ın "Etkileşimler" sayfası 3 sütunlu bir ızgara yapısındadır.
- **`row_start = 180`**: İlk resim satırının başladığı dikey nokta (piksel cinsinden).
- **`row_height = 130`**: Satırlar arasındaki mesafe.
- *İpucu:* Eğer Instagram arayüzünü güncellerse ve bot "boşluğa" tıklamaya başlarsa, `finder.py` kullanarak bu piksel değerlerini ayarlamanız gerekir.

### 🔃 Otomatik Filtreleme Mantığı
- **`apply_oldest_filter()`**: "Sırala ve Filtrele" butonuna tıklayıp "En Eskiden Yeniye" seçeneğini seçen gelişmiş bir fonksiyondur.
  - *Neden?* 2015 yılındaki geçmişinizi temizlemek, dünkü beğenilerinizi hemen kaldırmaktan çok daha güvenlidir.

---

## 🔐 4. `session_manager.py` — Oturum Koruma

- **`COOKIES_FILE = "cookies.json"`**: İlk manuel girişten sonra bot oturumunuzu buraya kaydeder.
- **`AutomationControlled`**: Playwright tarafından kontrol edildiğimizi gizlemek için `--disable-blink-features=AutomationControlled` argümanını kullanıyoruz.

---

## 🛠️ 5. Tanılama Araçları (Geliştiriciler İçin)

Bot durursa veya hata verirse ne olduğunu anlamak için bu scriptleri kullanın:

1. **`debug.py`**: Görsel bir tarayıcı açar ve her ağ isteğini günlüğe kaydeder. "Timeout" (Zaman Aşımı) hataları alıyorsanız buraya bakın.
2. **`finder.py`**: Hayati bir araçtır. Mevcut sayfayı tarar ve her butonun **X ve Y koordinatlarını** yazdırır.
3. **`detector.py`**: "Kalp" ikonunu analiz eder. Instagram buton kodlarını değiştirirse, bu araç yeni SVG yolunu veya ARIA etiketini tespit eder.

---

## ⚠️ Güvenlik İçin En İyi Pratikler

Hesabınızı %100 güvende tutmak için:
1. **Abartmayın:** Botu 7/24 çalıştırmayın. Günde 2-3 saat çalıştırıp bırakın.
2. **Manuel Aktivite:** Bot çalışmadığı zamanlarda ara sıra telefonunuzdan normal şekilde Instagram'a girip gezinin.
3. **IP Tutarlılığı:** Mümkünse botu, telefonunuzu bağladığınız Wi-Fi ağı üzerinden çalıştırın.

---

## 📝 Örnek Özelleştirme

**Senaryo:** Botun çok daha yavaş olmasını ve saatte sadece 10 beğeni kaldırmasını istiyorum.

1. `config.py` dosyasını açın.
2. `MAX_UNLIKE_PER_HOUR = 10` yapın.
3. `UNLIKE_DELAY = (60, 120)` yapın (Her işlem arası 1-2 dakika bekler).
4. Kaydedin ve `python main.py` komutuyla çalıştırın.

---
**Munliker** - *Gizlilik için tasarlandı, temizlik için inşa edildi.*
