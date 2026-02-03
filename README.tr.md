## Munliker ile Güvenli Instagram Geçmiş Temizliği
**Instagram toplu beğeni kaldırma** işlemi mi yapmak istiyorsunuz? **Munliker (Massive Unliker)**, kullanıcıların hesaplarını riske atmadan beğeni geçmişlerini silmelerine yardımcı olmak için tasarlanmış profesyonel bir **Instagram aktivite temizleyicidir**. **@miabeyefendi** tarafından geliştirilen bu araç, **Playwright** ve **insansı davranış simülasyonu** kullanarak dijital ayak izinizi temizlemeniz için en güvenli ve gizli (stealth) otomasyon deneyimini sunar.

# 🚀 Munliker: Gelişmiş Stealth Instagram Unlike Botu | By: @miabeyefendi

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python)](https://www.python.org/)
[![Playwright](https://img.shields.io/badge/Framework-Playwright-green.svg?style=for-the-badge&logo=playwright)](https://playwright.dev/)
[![Device](https://img.shields.io/badge/Device-Samsung_S24_Ultra-orange.svg?style=for-the-badge&logo=samsung)](https://github.com/Miabeyefendi/Munliker)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

[EN | Read in English](README.md) | [Teknik Rehber](egitim.md)

**Munliker**, insan davranışını taklit eden, yüksek performanslı bir Instagram aktivite temizleyicisidir.  
Şüpheli aktivite uyarılarına takılan klasik toplu unlike script’lerinin aksine Munliker, gelişmiş davranış simülasyonu sayesinde beğeni geçmişinizi güvenli biçimde temizler ve Instagram radarının altında kalır.

---

## 🔥 Neden Munliker?

Geleneksel botlar öngörülebilir **tıkla–tıkla–tıkla** desenleri izler.  
**Munliker**, gerçek bir mobil cihaz kullanan gerçek bir insan gibi davranarak bu deseni bozar.

- 🕵️ **Samsung Galaxy S24 Ultra Emülasyonu**  
  Ekran çözünürlüğü, dokunma davranışı ve Android 14 user-agent bilgileriyle güncel bir amiral gemisini birebir taklit eder.

- 🎭 **İnsanlaştırılmış Ara Aksiyonlar**  
  Beğeni kaldırma işlemleri arasında ana sayfa kaydırır, Reels izler ve DM’leri kontrol eder.

- 🔄 **Akıllı Kronolojik Temizlik**  
  Beğenileri otomatik olarak **Eskiden → Yeniye** sıralar; yıllar öncesinden güvenli temizlik sağlar.

- ⏳ **Dinamik Hız Kontrolü**  
  Sabit bekleme süreleri yerine rastgele, insani gecikmeler kullanır.

---

## ✨ Temel Özellikler

- **Gelişmiş Stealth**  
  `navigator.webdriver` dâhil olmak üzere bot tespit mekanizmalarına karşı önlemler.

- **Oturum Kalıcılığı**  
  Giriş oturumunu `cookies.json` dosyasına kaydeder; tekrar login gerekmez.

- **Otonom Filtreleme**  
  Instagram *Sırala ve Filtrele* arayüzünü tamamen otomatik yönetir.

- **Detaylı Loglama**  
  Anlık istatistikler ve işlem döngüleriyle temiz konsol çıktısı.

- **Önce Güvenlik**  
  Hesap kısıtlamalarını azaltmak için saatlik limitler içerir.

---

### Kurulum

Depoyu klonla:
```bash
git clone https://github.com/Miabeyefendi/munliker.git
cd munliker
```

Bağımlılıkları kur:
```bash
pip install playwright
playwright install chromium
```

Botu başlat:
```bash
python main.py
```

**Not:**  
İlk çalıştırmada manuel giriş için bir tarayıcı açılır.  
Instagram ana akışına ulaşıldığında oturum kaydedilir ve otomasyon başlar.

---

## 📖 Detaylı Rehber
- 📕 **Teknik Rehber** — `egitim.md`  
  Güvenli kullanım, hız ayarı ve cihaz profili özelleştirme rehberi.
---

## 📈 Sürüm Geçmişi

**v1.0.0**
- Samsung Galaxy S24 Ultra profil desteği
- Otomatik **Eskiden → Yeniye** filtreleme
- İnsan benzeri batch işleme (Reels / DM / Keşfet)
- Gelişmiş hata ayıklama için `finder.py` ve `debug.py`

---

## ⚠️ Sorumluluk Reddi & Güvenlik

Munliker **eğitsel amaçlarla** geliştirilmiştir.  
Instagram’ın otomasyon kullanımı Hizmet Şartları’na aykırıdır.

Geliştirici, hesap kısıtlamaları veya banlardan **sorumlu değildir**.

**Pro İpucu:**  
`MAX_UNLIKE_PER_HOUR` değerini **30’un altında** tutun ve botu sürekli çalıştırmayın.

---

## 🤝 Katkı

Katkılar memnuniyetle karşılanır.

1. Projeyi fork’layın
2. Feature branch oluşturun:
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. Değişiklikleri commit edin:
   ```bash
   git commit -m "Add AmazingFeature"
   ```
4. Branch’i gönderin:
   ```bash
   git push origin feature/AmazingFeature
   ```
5. Pull Request açın

---

## 👨‍💻 Geliştirici

**Miabeyefendi**
- GitHub: [@Miabeyefendi](https://github.com/Miabeyefendi)
- Proje: **Munliker** (Massive Unliker)

*Gizlilik ve otomasyon tutkusuyla geliştirildi.*
