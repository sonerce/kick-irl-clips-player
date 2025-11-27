# Kick.com BRB Clips Player

Kick.com yayıncılarının kliplerini rastgele sırada OBS'de oynatmak için basit bir HTML aracı.

## 🎬 Özellikler

- Kick.com API'sinden klipleri otomatik çekme
- Klipleri rastgele sırada karıştırma ve oynatma
- Otomatik klip değişimi (her klip süresi kadar)
- Tam ekran video oynatma
- OBS Browser Source için optimize edilmiş
- Tamamen client-side (sunucu gerektirmez)

## 📦 Dosyalar

- `index.html` - URL oluşturucu ana sayfa
- `clips.html` - Klip oynatıcı sayfa (OBS için)

## 🚀 Kullanım

### 1. URL Oluşturma

1. `index.html` dosyasını bir web tarayıcısında açın
2. Streamer adını girin (örn: "hype")
3. Zaman aralığını seçin (Day/Week/Month/All Time)
4. "Generate URL" butonuna tıklayın
5. Oluşturulan URL'yi kopyalayın

### 2. OBS'de Kullanım

1. OBS'de yeni bir **Browser Source** ekleyin
2. Kopyaladığınız URL'yi "URL" alanına yapıştırın
3. **Width (Genişlik)**: 1920
4. **Height (Yükseklik)**: 1080
5. ✅ "Shutdown source when not visible" seçeneğini işaretleyin
6. "OK" butonuna tıklayın

### 3. Direkt URL Kullanımı

URL'yi manuel olarak da oluşturabilirsiniz:

```
clips.html?streamerName=KANAL_ADI&duration=ZAMAN&clipDuration=SANIYE
```

**Örnek:**
```
clips.html?streamerName=hype&duration=week&clipDuration=30
```

**Parametreler:**
- `streamerName` - Kick.com kanal adı (zorunlu)
- `duration` - Zaman aralığı (varsayılan: week)
  - `day` - Son 24 saat
  - `week` - Son 7 gün
  - `month` - Son 30 gün  
  - `all` - Tüm zamanlar
- `clipDuration` - Her klip için gösterim süresi saniye cinsinden (varsayılan: 30)

## ⌨️ Klavye Kısayolları (Debug)

`clips.html` sayfasında klavye kısayolları kullanabilirsiniz:

- **Sağ Ok (→)** veya **Boşluk**: Sonraki klibe geç
- **R**: Klipleri yeniden karıştır ve başa dön

## 🔧 Teknik Detaylar

- Saf HTML, CSS ve JavaScript
- Harici kütüphane gerektirmez
- Kick.com API v2 kullanır (`/api/v2/channels/{username}/clips`)
- Responsive tasarım
- Otomatik klip süresi algılama
- Tüm klipler bittiğinde otomatik karıştırma

## 📝 Notlar

- Bu araç Kick.com'un public API'sini kullanır
- Klipler HLS format (m3u8) ile oynatılır, HLS.js kütüphanesi kullanılır
- API değişiklikleri durumunda güncelleme gerekebilir
- Kliplerin otomatik oynatılması için tarayıcıda autoplay izni gerekebilir
- OBS'de "Shutdown source when not visible" seçeneği performans için önerilir
- İlk klip sessiz (muted) başlayabilir, otomatik oynatma için gereklidir

## 🔍 Sorun Giderme

### Video Oynatmıyor
1. Tarayıcı console'unu açın (F12) ve hata mesajlarını kontrol edin
2. İnternet bağlantınızı kontrol edin (HLS stream gerektirir)
3. Farklı bir streamer/kanal deneyin
4. Tarayıcı önbelleğini temizleyin

### "Klipler yüklenemedi" Hatası
- Streamer adının doğru yazıldığından emin olun
- Belirtilen zaman aralığında klip olup olmadığını kontrol edin
- Kick.com API'sine erişimi engelleyen güvenlik duvarı/proxy kontrolü yapın

### OBS'de Siyah Ekran
- Browser Source genişlik/yüksekliğini kontrol edin (önerilen: 1920x1080)
- "Refresh browser when scene becomes active" seçeneğini işaretleyin
- OBS'yi yönetici olarak çalıştırmayı deneyin

## 🎯 Kullanım Senaryoları

1. **BRB (Be Right Back) Ekranı**: Yayından uzaklaştığınızda otomatik klip oynatma
2. **Break Screen**: Mola verirken kanal kliplerini gösterme
3. **Pre-Stream**: Yayın başlamadan önce klip montajı
4. **End Screen**: Yayın bitişinde klip gösterimi

## 📜 Lisans

MIT License - Özgürce kullanabilir ve değiştirebilirsiniz.

## 🤝 Katkı

Bu proje açık kaynaklıdır. İyileştirme önerilerinizi çekinmeden paylaşabilirsiniz.

---

**İlham kaynağı:** [IRL Tools Kick BRB Clips Player](https://irltools.github.io/KickBRBClipsPlayer/)
