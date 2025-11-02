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

### 10. İskele Etkileşimi ve 3. Sahne

#### İskele Diyalog Sistemi
- İskele pozisyonu otomatik hesaplanıyor (Caffè Nero'dan sonraki 2. büyük binadan sonra)
- Rakun iskeleye yaklaştığında "E" sembolü görünüyor
- İskele diyalog penceresi otomatik açılıyor
- Diyalog metni: "Büyükada ilk tatilimizi yapmaya gidiyoruz. Çok ilginç değil mi? Ilk defa bugün görüşüyoruz ama sanki yıllardır birbirimizi tanıyor gibiyiz."
- Cevap: "Evet, gerçekten! 💕"
- Diyalog bir kez gösterildikten sonra tekrar açılmıyor (`dockDialogShown` flag'i)

#### Caffè Nero Sonrası Hareket
- Caffè Nero diyalogu kapandıktan sonra kirpi iskeleye doğru hareket ediyor
- Kirpi diyalog baloncuğu: "Hadi koooooooş!! Vapuru kaçıracağız..Senin kadar hızlı koşamıyorum yahu beni bekle!!"
- Baloncuk metni çok satırlı olarak wrap ediliyor
- Kirpi ekrandan çıkmamak için durma mantığı Caffè Nero sonrası için de düzeltildi
- `canMoveWithBubble` flag'i ile kirpi baloncuk gösterirken hareket etmeye devam ediyor

### 11. Ada Sahnesi (4. Sahne)

#### Ada Sahne Oluşturulması
- Yeni sahne durumu: `game.sceneState = 'island'`
- İskele diyalog penceresi kapatıldığında otomatik ada sahnesine geçiliyor
- Ada sağ üst köşede konumlandırıldı
- Deniz tüm ekranı kaplıyor (mavi, dalga efektli)
- İskele sol alt köşede (ada sahnesinde ayrı bir iskele)
- Ada üzerinde ağaçlar, kumsal şeridi, gölge efekti

#### Ada Üzerinde Evler
- İlk ev: Ada'nın sağ tarafında (`islandX + 150, islandY - 80`)
- İkinci ev: Ada'nın ortasında (`islandX + 40, islandY + 50`)
- Her ev: Kahverengi gövde, kırmızı çatı, kapı, 2 pencere

#### Tekne Rota Sistemi
- Tekne objesi oluşturuldu (`boat` object)
- İskeleden başlayıp kıvrımlı bezier curve rotası ile adaya gidiyor
- Rota 3 bölümden oluşuyor:
  - Bölüm 1: İskeleden aşağı ve sağa doğru
  - Bölüm 2: Ada'nın altından geçerek sağa ve yukarı
  - Bölüm 3: Ada'nın sol tarafından yukarıdan, ortasına, alt kısmına (`islandY + 110`)
- Tekne rotasında açı otomatik hesaplanıyor (hareket yönüne göre)
- Tekne animasyonlu olarak rotada hareket ediyor
- Ada sahnesine geçildiğinde tekne otomatik başlıyor

#### Test Modu
- Oyun direkt ada sahnesinden başlıyor (test için)
- `game.state = 'playing'`, `game.sceneState = 'island'`
- Tekne otomatik initialize ediliyor

### 12. Kod İyileştirmeleri

#### Kirpi Hareket Sistemi Düzeltmeleri
- Caffè Nero sonrası kirpi ekrandan çıkmamak için durduğunda `waitingForPlayer` flag'i set ediliyor
- Rakun hareket ettiğinde `targetX` null ise yeni hedef belirleniyor
- Kirpi hareket logları temizlendi (production için)

#### İskele Etkileşim İyileştirmeleri
- İskele etkileşim mesafesi genişletildi (150px ön ve arka)
- İskele kontrolü her frame çalışıyor
- İskele logları temizlendi

### 13. onIsland Sahnesi İyileştirmeleri

#### İskele, Deniz ve Tekne Ekleme
- onIsland sahnesine son evden sonra iskele, deniz ve tekne eklendi
- İskele pozisyonu: Son evden 100 piksel sonra (son evin sağından başlıyor)
- Deniz: İskele başlangıcından itibaren tüm sağ taraf deniz olarak çiziliyor
- Tekne: İskelenin sonuna halatla bağlı, denize paralel duruyor
- Tekne bayrağı: Tekneye bitişik kırmızı bayrak
- Halat bağlantı noktaları: Hem iskele üzerinde hem tekne üzerinde görünüyor
- Deniz dalga efektleri eklendi

#### İskele Görsel Detayları
- İskele kazıkları (bacaklar): İlk 3 bacak çizilmiyor (sadece son 3 bacak görünüyor)
- İskele platformu: Ahşap görünümlü kahverengi platform
- İskele kazıkları: Suya doğru uzanan kahverengi dikey çubuklar

#### Karakter Sınırları Güncellemesi
- **Gameplay sahnesi**: Rakun ve kirpi iskele başlangıcına (`dockX`) kadar gidebilir, daha ileriye gidemez
- **onIsland sahnesi**: Rakun ve kirpi iskele başlangıcına (`islandDockX`) kadar gidebilir, daha ileriye gidemez
- Her iki sahnede de karakterler iskele üzerine çıkamıyor

#### Kamera Sınırları Genişletme
- onIsland sahnesinde kamera sınırları iskele sonundan 800 piksel daha sağa genişletildi
- Böylece deniz, iskele ve tekne tamamen görünür oluyor
- Karakter sınırları iskele başlangıcında, kamera iskele sonundan 800 piksel sonrasına kadar takip edebiliyor

### 14. Tekne Rotası ve Ada Sınırları

#### Tekne Rotası Ada Sınırları İyileştirmesi
- Tekne rotası kontrol noktaları adanın üzerine çıkmayacak şekilde güncellendi
- Ada sınır kontrolü eklendi (`isPointOnIsland` fonksiyonu)
- Tüm kontrol noktaları ada'nın dışında kalacak şekilde ayarlandı
- Tekne ada kenarına yakın ama üzerine çıkmadan hareket ediyor

### 15. onIsland Sahnesi Zemin Değişikliği

#### Zemin Görseli Güncellendi
- onIsland sahnesindeki zemin `ground_pref.png` yerine ilk sahnedeki gibi gri kaldırım olarak değiştirildi
- X ve Y pozisyonları korundu, sadece görsel değişti
- İlk sahnedeki kaldırım stili (#C0C0C0 gri zemin, üst ve alt gölge efektleri) kullanılıyor

### 16. Caffè Nero E İşareti Pozisyonu

#### Etkileşim İşareti İyileştirmesi
- Caffè Nero binası için "E" işareti binanın üst kenarından 10 pixel yukarıda görünecek şekilde ayarlandı
- Bina yüksekliği dinamik olarak hesaplanıyor
- İşaret binanın gerçek pozisyonuna göre doğru konumda görünüyor

### 17. onIsland İskele Etkileşimi ve Ters Tekne Rotası

#### İskele Etkileşimi Eklendi
- onIsland sahnesinde otel etkileşimi tamamlandıktan sonra iskeleye yaklaşınca "E" işareti görünüyor
- İskele etkileşimi için `openIslandDockDialog()` fonksiyonu eklendi
- Diyalog metni: "Büyükada ilk tatilimizi yapmaya gidiyoruz. Çok ilginç değil mi? Ilk defa bugün görüşüyoruz ama sanki yıllardır birbirimizi tanıyor gibiyiz."
- Cevap: "Evet, gerçekten"
- Diyalog kapatıldığında `islandReturn` sahnesine geçiliyor

#### Ters Tekne Rotası
- `getBoatPositionReturn()` fonksiyonu eklendi - adadan iskeleye giden ters rota
- Yeni sahne durumu: `islandReturn` (adadan iskeleye dönüş)
- Tekne rotası orijinal rotanın tam tersi olarak hesaplanıyor
- Tekne adadan başlayıp iskeleye gidiyor (ilk rota: iskeleden adaya)
- Tekne iskeleye ulaştığında `gameplay` sahnesine geri dönülüyor
- `updateBoat()` fonksiyonu hem `island` hem `islandReturn` sahneleri için çalışıyor
- `drawBoat()` fonksiyonu her iki sahne için de tekne çiziyor

### 18. returningHome Sahnesi ve Modern Araba

#### returningHome Sahnesi Oluşturuldu
- Yeni sahne durumu: `returningHome` (adadan dönüş, eve yürüme sahnesi)
- Tekne adadan iskeleye döndüğünde `returningHome` sahnesine geçiliyor
- Sahne yapısı: İskele (sol), deniz, evler (home1, home2, home1, home2, hotel, home1)
- Hotel oyuncunun evi olarak belirlendi
- `onIsland` sahnesi ile benzer sokak yapısı (evler, dekorasyonlar, çitler)
- Dekorasyon sistemi `onIsland` ile aynı mantıkla çalışıyor

#### İskele ve Tekne Düzeni
- İskele sahnenin solunda, deniz iskele solunda başlıyor
- Tekne en solda, halat tekne ile iskele arasında, iskele sağda
- İskele bacakları: Soldan başlayarak sağdan 2. bacağa kadar çiziliyor (sağdan 2. bacak ve en sağdaki çizilmiyor)
- Yol başlangıcı: İskele sağdan 2. bacağın x koordinatından başlıyor
- Deniz alanı: Yol başlangıcına kadar uzanıyor

#### Modern Beyaz Araba
- Hotel önüne modern beyaz araba eklendi
- Yuvarlatılmış köşeler (quadratic curves ile)
- Gradient efektleri (gövde, camlar, highlights)
- Detaylar: Ön farlar, arka lambalar, cam yansımaları, kapı çizgisi
- Modern alaşım jantlar (5 kollu yıldız deseni)
- Gölge efektleri ve derinlik
- Araba boyutu: 160x55 piksel
- Araba pozisyonu: Hotel merkezinden 80px sola (hotel önünde ortalanmış)

### 19. Arabaya Binme ve Hareket Sistemi

#### Kirpi Yönlendirme Sistemi
- returningHome sahnesinde kirpi arabaya doğru otomatik hareket ediyor
- Kirpi'nin diyalog baloncuğu: "Hadi doğru arabaya! Ama sen sür olur mu ben biraz uyuyacağım. :)"
- Kirpi ekrandan çıkmamak için durma mantığı (onIsland ile aynı)
- Kirpi arabaya ulaşınca bekliyor

#### Araba Etkileşim Sistemi
- Arabanın önüne yaklaşınca "E" sembolü görünüyor (evin yüksekliğinde +20px)
- E tuşuna basınca arabaya binme diyalogu açılıyor
- Diyalog metni: "Evet boncuk, arabaya geldik. Hadi hazırsan yola çıkalım.💕"
- "Hadi gidelim" butonuna tıklandığında karakterler kayboluyor ve araba hareket ediyor

#### Araba Hareket Animasyonu
- `game.carMoving` flag'i ile araba hareket kontrolü
- Araba sağa doğru (+x yönünde) 5 piksel/frame hızında hareket ediyor
- Kamera arabayı takip ediyor (arabaya kilitleniyor)
- Araba ekrandan çıktığında hareket duruyor
- Karakterler arabaya binince görünmüyor (`game.carEntered` kontrolü)

#### Görsel Düzenlemeler
- Çizim sırası düzeltildi: Araba önce, karakterler sonra çiziliyor (rakun her zaman önde)
- Yol ekranın sonuna kadar uzatıldı (kamera pozisyonu + canvas genişliği + 500px)
- Ekranın sonundaki boşluk dolduruldu

#### Kod İyileştirmeleri
- `updateCar()` fonksiyonu eklendi (araba hareket güncellemesi)
- `carX` pozisyonu arabaya binildikten sonra yeniden hesaplanmıyor (hareket için)
- Kamera sistemi arabaya binme durumunu destekliyor

### 20. Istanbul-Datça Yolculuk Sahnesi

#### Yeni Sahne Oluşturuldu
- Yeni sahne durumu: `istanbulDatca` (araba ile yolculuk sahnesi)
- Araba `returningHome` sahnesinde ekrandan çıktığında otomatik geçiş
- Gökyüzü gradient arka plan (açık mavi tonları)
- Araba rotası sistemi: `roadTripCar` objesi ile rota takibi

#### 3 Satırlı Zigzag Rota Sistemi
- **Satır 1**: Sol → Sağ (tamamen)
- **Geçiş 1**: Sağ üst → Sağ orta (smooth bezier curve, X+ ekseninde uzatılmış)
- **Satır 2**: Sağ → Sol (tamamen)
- **Geçiş 2**: Sol orta → Sol alt (smooth bezier curve)
- **Satır 3**: Sol → Sağ (tamamen, Datça'ya)
- Bezier curve ile smooth geçişler
- Progress tabanlı rota hesaplama (`getRoadTripPosition`)

#### Yol Çizim Sistemi
- **Snake Game Mantığı**: Tüm yol baştan çiziliyor (araba geçtikçe değil)
- Yol sprite kullanımı: `ground_pref.png` ile pattern fill
- Fallback: Sprite yoksa asfalt görünümlü yol (gri, beyaz kenarlar, sarı orta çizgi)
- Segment interpolasyonu: Geçiş bölümlerinde daha fazla nokta
- Polygon tabanlı yol çizimi (kenarlar dinamik hesaplanıyor)
- Yol genişliği: 60px

#### Tabela Sistemi
- **Istanbul Tabelası**: Sol üst köşe (x=20, y=20)
- **Datça Tabelası**: Sağ alt köşe (canvas.width - 160, canvas.height - 120)
- Beyaz dikdörtgen arka plan, siyah kenarlık
- Kahverengi direk (her tabelanın altında)
- Tabelalar yolun ve arabanın üstünde çiziliyor (z-order)
- Canvas transform sıfırlama ile arabanın transform'larından etkilenmiyor

#### Yol Pozisyon Ayarları
- **Yol başlangıcı**: Istanbul tabelasının bittiği pixel'den +5 pixel sonra
- **Yol bitişi**: Datça tabelasının başladığı yerden 10px önce
- **Araba pozisyon düzeltmesi**: Araba merkezi yol sonuna geldiğinde yarısı dışarı taşmamalı
- Araba genişliği hesabı ile yol bitiş noktası ayarlandı

#### Pathing İyileştirmeleri
- Geçiş bölümlerinde 5 kat daha fazla segment (smooth görünüm)
- Segment interpolasyonu: Büyük boşluklar için ara noktalar
- Toplam 300+ segment ile yüksek çözünürlüklü rota
- Araba rotası ile yol segmentleri birebir eşleşiyor
