# Rakun ve Kirpi Platformer Quiz Oyunu - TODO Listesi

## 🎮 Proje Özeti
Kız arkadaşı için doğum günü hediyesi olarak özel bir 2D platformer quiz oyunu. Ana karakter Rakun (kiz arkadaş), yardımcı karakter Kirpi (erkek arkadaş). Oyuncu nesnelerle etkileşime girerek özel sorular cevaplayacak ve seviyeyi tamamlayacak.

---

## 📋 Geliştirme Aşamaları

### 1. Temel Kurulum ve Yapı
- [ ] HTML dosyası oluştur (index.html)
- [ ] Canvas tabanlı oyun motoru kur
- [ ] Temel dosya yapısını organize et
- [ ] Oyun döngüsü (game loop) oluştur

### 2. Karakter Geliştirme
- [ ] Rakun karakteri tasarla ve çiz
  - [ ] Durma animasyonu
  - [ ] Yürüme animasyonu
  - [ ] Zıplama animasyonu
- [ ] Kirpi karakteri tasarla ve çiz
  - [ ] Statik görünüm
  - [ ] Diyalog anında animasyon
- [ ] Karakter fizik mekanikleri
  - [ ] Sağa/sola hareket
  - [ ] Zıplama mekaniği
  - [ ] Yerçekimi simülasyonu
  - [ ] Zemin ve platform çarpışma kontrolü

### 3. Seviye Tasarımı
- [ ] Platform sistemi oluştur
- [ ] Zemin ve duvar çarpışma sistemi
- [ ] Etkileşimli nesneler ekle:
  - [ ] Kapılar (kilitli/açık)
  - [ ] Anahtarlar
  - [ ] Quiz noktaları (özel objeler)
  - [ ] Checkpoint noktaları
- [ ] Seviye haritası tasarla (3-5 alan/oda)
- [ ] Arka plan grafikleri

### 4. Quiz ve Diyalog Sistemi
- [ ] Diyalog kutusu UI tasarımı
  - [ ] Konuşma balonu stili
  - [ ] Karakter portre alanı
  - [ ] Metin gösterim alanı
  - [ ] Cevap butonları
- [ ] Etkileşim sistemi
  - [ ] Nesneye yaklaşma algılama
  - [ ] "E tuşuna bas" göstergesi
  - [ ] Diyalog açma/kapama
- [ ] Soru-cevap mekanizması
  - [ ] Soru havuzu yapısı
  - [ ] Çoktan seçmeli cevaplar (2-3 şık)
  - [ ] Doğru/yanlış kontrolü
  - [ ] Cevap sonrası feedback
- [ ] İpucu sistemi (Kirpi'den yardım)

### 5. Oyun Mekaniği ve Akış
- [ ] Seviye ilerlemesi
  - [ ] Doğru cevap = kapı açılır/engel kalkar
  - [ ] Yanlış cevap = tekrar deneme/ipucu
- [ ] Ilerleme takibi
  - [ ] Kaç soru doğru cevaplanmış
  - [ ] Hangi bölgeler keşfedilmiş
- [ ] Checkpoint sistemi
- [ ] Oyun sonu ekranı
  - [ ] Kutlama animasyonu
  - [ ] Özel mesaj gösterimi
  - [ ] "Tekrar oyna" butonu

### 6. Görsel ve Ses Tasarımı
- [ ] Karakter çizimleri (basit pixel art veya geometrik şekiller)
- [ ] Platform ve nesne grafikleri
- [ ] Arka plan tasarımı (romantik/doğal tema)
- [ ] UI elemanları
  - [ ] Diyalog kutusu
  - [ ] Butonlar
  - [ ] İkonlar
- [ ] Opsiyonel: Basit müzik/ses efektleri
  - [ ] Zıplama sesi
  - [ ] Doğru cevap sesi
  - [ ] Yanlış cevap sesi
  - [ ] Arka plan müziği

### 7. İçerik ve Kişiselleştirme
- [ ] Sorular ve cevaplar (kullanıcıdan alınacak):
  - [ ] Soru 1: [Kullanıcı dolduracak]
  - [ ] Soru 2: [Kullanıcı dolduracak]
  - [ ] Soru 3: [Kullanıcı dolduracak]
  - [ ] Soru 4: [Kullanıcı dolduracak]
  - [ ] Soru 5: [Kullanıcı dolduracak]
  - [ ] Soru 6: [Kullanıcı dolduracak]
- [ ] Kirpi diyalogları ve ipuçları
- [ ] Oyun sonu mesajı (doğum günü mesajı)
- [ ] Özel tarih/isim ekleme

### 8. Optimizasyon ve Test
- [ ] Farklı ekran boyutlarında test
- [ ] Mobil uyumluluk (opsiyonel)
- [ ] Performans optimizasyonu
- [ ] Bug tespiti ve düzeltme
- [ ] Zorluk dengesi ayarlama

### 9. Son Rötuşlar
- [ ] Geçiş animasyonları
- [ ] Parçacık efektleri (kalpler, yıldızlar)
- [ ] Loading ekranı
- [ ] Başlangıç menüsü
- [ ] Kontroller açıklaması (WASD/Arrow keys, E tuşu)

---

## 🎨 Tasarım Kararları (Kullanıcıdan Bekleyen)

### Sorular
```
SORU 1:
- Soru metni: ?
- Şık A: ?
- Şık B: ?
- Şık C: ?
- Doğru cevap: ?

SORU 2:
- Soru metni: ?
- Şık A: ?
- Şık B: ?
- Şık C: ?
- Doğru cevap: ?

[Devamı kullanıcı ekleyecek...]
```

### Görsel Tercihler
- [ ] Renk paleti: ?
- [ ] Grafik stili: (Pixel art / Geometrik / Cartoon)
- [ ] Tema: (Orman / Bahçe / Fantezi / Modern)

### Özel Mesajlar
- [ ] Oyun başlangıç mesajı: ?
- [ ] Oyun sonu mesajı: ?
- [ ] Doğum günü mesajı: ?

---

## 🛠️ Teknik Detaylar

### Teknoloji Stack
- HTML5 Canvas
- Vanilla JavaScript (ES6+)
- CSS3 (styling için)

### Temel Sınıflar
```
- Game (ana oyun yöneticisi)
- Player (Rakun karakteri)
- NPC (Kirpi karakteri)
- Platform (zemin ve platformlar)
- InteractiveObject (quiz nesneleri, kapılar, vb.)
- DialogSystem (diyalog yönetimi)
- QuizManager (soru-cevap sistemi)
- CollisionDetector (çarpışma kontrolü)
- InputHandler (klavye kontrolleri)
```

### Dosya Yapısı
```
/game
  ├── index.html
  ├── styles.css
  ├── game.js (ana oyun mantığı)
  ├── player.js (karakter kontrolleri)
  ├── dialog.js (diyalog sistemi)
  ├── quiz.js (soru-cevap)
  └── assets/
      ├── sprites/ (karakter ve nesne görselleri)
      └── sounds/ (opsiyonel sesler)
```

---

## 📝 Notlar
- Oyun tarayıcıda çalışacak (HTML5)
- Tek dosyada da geliştirilebilir (hızlı prototip için)
- Grafikleri başta basit tutup sonra geliştirilebilir
- İlk versiyon 2-3 soru ile test edilmeli
- Kullanıcı feedback'i alındıktan sonra genişletilebilir

---

## 🚀 Öncelikli Görevler (İlk Sprint)
1. Temel karakter hareketi ve platformer mekaniği
2. Basit bir seviye tasarımı (1 oda)
3. Tek bir etkileşimli nesne ve diyalog sistemi
4. 1-2 test sorusu
5. Temel görsel tasarım

---

## ✅ Başarı Kriterleri
- [ ] Rakun karakteri sorunsuz hareket ediyor
- [ ] Nesnelerle etkileşim çalışıyor
- [ ] Sorular gösteriliyor ve cevaplanabiliyor
- [ ] Doğru cevaplarla ilerleme sağlanıyor
- [ ] Kirpi karakteri uygun yerlerde görünüyor
- [ ] Oyun baştan sona oynanabiliyor
- [ ] Özel mesajlar ve isimler doğru yerleştirilimiş
- [ ] Oyun romantik ve eğlenceli atmosfere sahip