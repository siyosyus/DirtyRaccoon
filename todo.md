# DirtyRaccoon - Oyun Geliştirme Todo Listesi

## ✅ Tamamlanan Özellikler

### 1. Görsel İyileştirmeler ve Bina Sistemi

#### Bina Yerleştirme Pattern'i
- **2 küçük, 1 büyük** bina pattern'i uygulandı
- Dinamik bina aralıkları (her binanın gerçek genişliği + 20px minimum boşluk)
- 30 bina harita boyunca yerleştirildi
- Z-order (çizim sırası) X pozisyonuna göre düzenlendi (soldaki binalar arkada, sağdakiler önde)

#### Bina Spriteları
- Buildings klasöründen sprite'lar yüklendi:
  - Blank Shops (renkli boş mağazalar)
  - Muted Colour (pastel renkli binalar)
  - Normal (normal renkli binalar)
  - Themed Shops - Large (büyük temalı dükkanlar)
  - Themed Shops - Small (küçük temalı dükkanlar)

#### Caffè Nero Branding
- İlk büyük içecek satan bina (largeBar) otomatik tespit edildi
- Binanın tente kısmına "Caffè Nero" yazısı eklendi
- Mavi renk (#0066CC), bold 32px font
- Beyaz outline ile okunabilirlik artırıldı
- Yazı pozisyonu tente üzerine hizalandı

### 2. Zemin ve Kaldırım Sistemi

#### Kaldırım Zemin
- Basit düz gri kaldırım çizimi (#C0C0C0)
- Üst ve alt kenarlarda hafif gölge efektleri
- Karakterler kaldırım üzerinde duruyor (groundLevel = 550)

#### Pavement Tile Sorunu Çözüldü
- Pavement tile (buildings/Normal/pavement.png) içindeki gri duvarlar sorunu
- Tile kaldırıldı, basit kod çizimi kullanılıyor

### 3. Diyalog Sistemi

#### Açılış Diyaloğu
- Kirpi karakteri rakun'a doğru yürüyor
- Etkileşim mesafesine geldiğinde otomatik diyalog açılıyor
- "Hazırım! 💕" butonu ile diyalog kapatılıyor

#### Diyalog Pencere İyileştirmeleri
- Text wrapping (metin sarma) fonksiyonu eklendi
- Çok satırlı metin desteği
- Dinamik yükseklik ayarlaması
- Dialog.text ve dialog.text2 desteği

#### Konuşma Baloncuğu
- Kirpi'nin kafasının üstünde küçük konuşma baloncuğu
- "Bir kahve mi içsek acaba?" metni
- Sadece gameplay sahnesinde ve belirli durumlarda görünüyor
- Beyaz arka plan, siyah kenarlık, yuvarlatılmış köşeler

### 4. Kirpi (Hedgehog) Hareket Sistemi

#### Açılış Sahnesi (Opening)
- Kirpi otomatik olarak rakun'a doğru yürüyor
- Rakunun soluna veya sağına göre pozisyon alıyor
- Etkileşim mesafesinde duruyor ve diyalog açıyor

#### Gameplay Sahnesi
- **Caffè Nero'ya Gitme**: "Hazırım" butonuna tıklandığında kirpi Caffè Nero binasına doğru hareket ediyor
- **Rakun Durduğunda**: 
  - Kirpi ekrandan çıkacaksa, ekranın %70'lik pozisyonuna gelip duruyor
  - Baloncuk gösteriyor ve rakunun hareket etmesini bekliyor
  - `waitingForPlayer` flag'i ile durum takip ediliyor
- **Rakun Hareket Ettiğinde**: Kirpi Caffè Nero'ya gitmeye devam ediyor

#### Hız Ayarı
- Rakun hızı: 5 piksel/frame
- Kirpi hızı: 3.75 piksel/frame (güncellendi)

### 5. Sahne Geçişleri

#### Opening → Gameplay Geçişi
- "Hazırım" butonuna tıklandığında opening sahnesinden gameplay'e geçiliyor
- Spotlight ve siyah ekran kayboluyor
- Normal oyun ekranı (gökyüzü, binalar, karakterler) görünüyor

### 6. Kamera Sistemi

- Kamera rakun'u takip ediyor
- X ekseninde takip (Y ekseni sabit)
- Kamera sınırları (harita dışına çıkmıyor)

### 7. Arka Plan Elemanları

#### Gökyüzü Gradient
- 3 renk geçişi: Açık mavi (#B0E0E6) → Gökyüzü mavisi (#87CEEB) → Çok açık mavi (#E0F6FF)
- Zengin görünüm

#### Bulutlar
- Paralax scrolling efektli bulutlar
- Buildings klasöründen bulut sprite'ları yüklendi
- 6 farklı bulut pozisyonu

### 8. Animasyon Sistemi

#### Rakun Animasyonları
- Idle (durma) animasyonu - 11 frame
- Walk (yürüme) animasyonu - 11 frame
- Jump (zıplama) animasyonu - 1 frame

#### Kirpi Animasyonları
- Idle sprite sheet animasyonu
- Move sprite sheet animasyonu
- Sprite sheet'lerden frame'ler çıkarılıyor

### 9. Teknik İyileştirmeler

#### Sprite Yükleme
- Tüm bina sprite'ları için hata yakalama
- Sprite yüklenme kontrolü (complete ve width > 0)
- Debug console log'ları

#### Performans
- Sadece ekranda görünen binaları çizme
- Gereksiz hesaplamaları önleme

#### Bina Pozisyon Hesaplama
- `calculateBuildingPositions()` fonksiyonu ile başlangıçta bir kez hesaplama
- Caffè Nero binasının pozisyonu otomatik kaydediliyor

## 🔄 Devam Eden / İyileştirme Gereken Özellikler

- [ ] Kirpi'nin ekran pozisyonuna gelme mantığının test edilmesi ve iyileştirilmesi
- [ ] Diyalog baloncuğunun daha smooth görünmesi için animasyon eklenmesi
- [ ] Bina sprite'larının yüklenme durumunun daha iyi yönetilmesi

## 📝 Notlar

- Buildings klasörü git'e eklendi
- Tüm görsel iyileştirmeler commit edildi
- Caffè Nero branding özelliği tamamlandı
- Kirpi hareket sistemi geliştirildi ve optimize edildi
- Kirpi hızı 2'den 3.75'ye güncellendi

## 🎯 Son Değişiklikler (En Son Commit'ten Önce)

### Kirpi Hareket Sistemi İyileştirmeleri
- `waitingForPlayer` flag'i eklendi (rakunun hareket etmesini bekliyor mu?)
- `screenTargetX` eklendi (ekran pozisyon hedefi)
- Rakun durduğunda kirpi ekranın %70'lik pozisyonuna gelip duruyor
- Rakun hareket ettiğinde kirpi Caffè Nero'ya gitmeye devam ediyor
- Ekran hedefi her frame güncelleniyor (kamera hareket edebilir)

### Hız Ayarı
- Kirpi hızı 2 piksel/frame → 3.75 piksel/frame olarak güncellendi
