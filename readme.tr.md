[EN | Read in English](README.md)

**Munliker**, Instagram etkileşimlerinizi temizlemek için tasarlanmış, "insan gibi" davranan akıllı bir araçtır. Sıradan botların aksine Munliker; Reels izleme, Keşfet'te gezinme ve DM kontrolü gibi gerçek kullanıcı hareketlerini taklit ederek hesabınızın banlanma riskini minimize eder.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Playwright](https://img.shields.io/badge/Framework-Playwright-green.svg)
![Cihaz](https://img.shields.io/badge/Cihaz-Samsung_S23_FE-orange.svg)

---

## ✨ Özellikler

- **🕵️ Gelişmiş Gizlilik:** Gerçekçi User-Agent, ekran çözünürlüğü ve dokunma hareketleri ile Samsung Galaxy S23 FE cihazını emüle eder.
- **🎭 İnsan Mantığı:** Beğeni kaldırma işlemleri arasında rastgele ana sayfa gezintisi, Reels izleme ve DM kontrolü yapar.
- **⏳ Akıllı Limitler:** Instagram radarına takılmamak için saatlik limitler ve rastgele bekleme süreleri (delay) içerir.
- **🔄 Otomatik Filtreleme:** Beğenilenler sayfasını "En Eskiden Yeniye" şeklinde otomatik sıralayarak geçmişten bugüne temizlik yapar.
- **📂 Oturum Yönetimi:** `cookies.json` desteği sayesinde her seferinde giriş yapmanız gerekmez.

---

## 🛠️ Kurulum

1. **Depoyu klonlayın:**
```bash
git clone https://github.com/kullaniciadin/munliker.git
cd munliker
```

2. **Gerekli kütüphaneleri yükleyin:**
```bash
pip install playwright
playwright install chromium
```

3. **Botu başlatın:**
```bash
python main.py
```

---

## 📖 Yapılandırma Rehberi

Botun davranışlarını şu dosyalardan özelleştirebilirsiniz:

- **`config.py`**: Ana ayar dosyası. Saatlik limitleri (`MAX_UNLIKE_PER_HOUR`), gecikme sürelerini ve cihaz profilini buradan değiştirin.
- **`human_actions.py`**: Kaç adet Reels izleneceği veya Keşfet'te kaç kez kaydırma yapılacağı gibi "dolgu" hareketleri ayarlayın.
- **`unlike_manager.py`**: Beğeni kaldırma mantığını ve tıklama koordinatlarını düzenleyin.
- **`ui.py`**: Konsol çıktılarını ve görsel loglama stilini kişiselleştirin.

---

## ⚠️ Uyarı

Bu araç sadece eğitim amaçlıdır. Instagram üzerinde bot kullanmak platformun hizmet şartlarını ihlal edebilir. Oluşabilecek hesap kısıtlamalarından geliştirici sorumlu değildir. **Tavsiye:** Güvenlik için saatlik 30 beğeni kaldırma limitini aşmayın.

---

## 🤝 Katkıda Bulunun

Hataları bildirmekten veya yeni özellik önerileri için *Pull Request* göndermekten çekinmeyin!

---
**Munliker** - *Geçmişi temizle, hesabını güvende tut.*
