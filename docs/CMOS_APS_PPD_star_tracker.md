# CMOS APS - PPD - Star Tracker Teknik Notu

## CMOS APS, Pinned Photodiode (PPD) ve Foton Soğurulması

### Star Tracker Sensör Mimarisi Açısından Teknik İnceleme

## 1. CMOS APS ve Pinned Photodiode (PPD) Yapısı

Star tracker mimarisinde CCD yerine çoğunlukla CMOS APS (Active Pixel Sensor) tercih edilir. Bunun temel nedeni, CMOS APS yapısının uzay radyasyonuna karşı daha dayanıklı olması ve her pikselin kendi amplifikatörünü içermesidir. Bu mimaride pikselin opto-elektronik olarak en kritik bölümü Pinned Photodiode (PPD) yapısıdır.

Sıradan bir p-n diyot yerine `p+ - n - p` yapısına sahip pinned photodiode kullanılır. Kesit yapısı aşağıdaki gibi özetlenebilir:

| Katman | Görev / Açıklama | Yaklaşık doping |
| --- | --- | --- |
| Yüzey pasivasyon tabakası (`SiO₂`) | Silisyum yüzeyini koruyan oksit tabakasıdır. | - |
| `p+` pinning layer | Yüzeyi deliklerle doyurarak yüzey kaynaklı elektron üretimini bastırır. | `N_A ≈ 10^18 cm^-3` |
| `n`-type buried well / kuyu | Fotonla üretilen elektronların toplandığı aktif hacimdir. | `N_D ≈ 10^16 cm^-3` |
| `p`-type substrate / substrat | Sensörün taban silisyum bölgesidir. | `N_A ≈ 10^15 cm^-3` |

Bu yapının kullanılmasının iki kritik sebebi vardır:

### 1.1. Arayüz Tuzaklarının Pasivasyonu ve Dark Current Kontrolü

Silisyum ile üzerindeki koruyucu `SiO₂` tabakasının birleştiği yüzey arayüzünde (`surface interface`) çok sayıda kristal kusuru, yani `dangling bond` bulunur. Bu kusurlar termal olarak elektron üretip doğrudan piksele sızabilir. Bu istenmeyen sinyal karanlık akım olarak görülür.

Yüzeye yerleştirilen yoğun dop edilmiş ince `p+` tabakası, yüzeyi deliklerle (`holes`) doyurur. Yüzeyde termal olarak oluşan serbest elektronlar bu deliklerle hızlı şekilde rekombine olur. Böylece star tracker sensörleri için kritik bir gürültü kaynağı olan yüzey kaynaklı karanlık akım önemli ölçüde bastırılır.

### 1.2. Gömülü Kanal (Buried Channel)

Işıkla üretilen elektronlar, yüzeyden uzakta; `p+` tabakası ile `p`-substrate arasında kalan `n`-tipi bölgede, yani gömülü kuyuda toplanır. Bu sayede yük taşıyıcıları yüzey arayüzündeki tuzaklardan ve yüzey gürültüsünden izole edilmiş olur.

## 2. Silisyumun Optik Soğurma Fiziği ve Fonon Katkısı

Silisyum, dolaylı bant aralığına sahip bir yarıiletkendir. Bant aralığı yaklaşık `E_g = 1.12 eV` değerindedir. Bu durum, foton soğurulmasının doğrudan bant aralıklı yarıiletkenlere göre daha farklı gerçekleşmesine neden olur.

Doğrudan bant aralıklı yarıiletkenlerde, örneğin `GaAs`'ta, bir elektronun valans bandından iletim bandına geçmesi için foton enerjisinin yeterli olması çoğu durumda yeterlidir. Ancak silisyumda valans bandının tepe noktası ile iletim bandının taban noktası kristal momentum uzayında farklı konumlardadır. Bu nedenle yalnızca enerji korunumu değil, momentum korunumu da sağlanmalıdır.

Bu yüzden silisyumda fotonun soğurulabilmesi için kristal örgü titreşimlerinin kuantumu olan fonon sürece dahil olur. Bu mekanizma `fonon yardımlı (phonon-assisted) soğurma` olarak adlandırılır.

Enerji korunumu:

```text
E_final = E_initial + hν ± E_phonon
```

Momentum korunumu:

```text
k_final = k_initial + k_photon ± k_phonon
```

- Foton momentumu, elektron momentumu yanında ihmal edilecek kadar küçüktür: `k_photon ≈ 0`
- Bu nedenle momentum değişimini esas olarak örgü titreşimi, yani fonon üstlenir.
- Fonon yardımlı süreç olasılığı daha düşük olduğundan silisyumun soğurma katsayısı `α`, dalga boyuna bağlı olarak ciddi biçimde değişir ve bazı fotonlar silisyumun daha derin bölgelerine nüfuz edebilir.

## 3. Penetrasyon Derinliği: Dalga Boyu, Soğurma Katsayısı ve Sensör Derinliği

Fotonların silisyum içinde katettiği ortalama soğurulma mesafesi, penetrasyon ya da nüfuz derinliği olarak ifade edilir. Temel ilişki şöyledir:

```text
L_abs = 1 / α(λ)
```

Burada `α(λ)`, dalga boyuna bağlı soğurma katsayısıdır. `α` büyüdükçe foton daha yüzeyde soğurulur; `α` küçüldükçe foton daha derine ilerleyebilir.

| Işık bölgesi | Dalga boyu | Soğurma katsayısı | Yaklaşık `L_abs` | Sensör açısından anlamı |
| --- | --- | --- | --- | --- |
| Morötesi / mavi | `400 nm` | `α ≈ 10^5 cm^-1` | `≈ 0.1 µm` | Yüzeye çok yakın soğurulur. |
| Kırmızı / kızılötesi | `800 nm` | `α ≈ 10^3 cm^-1` | `≈ 10 µm` | Daha derin bölgelerde soğurulur. |

Bu bölüm star tracker açısından önemlidir; çünkü yıldız ışığından gelen fotonun sensör içinde nerede soğurulduğu, oluşan elektronun hangi mekanizma ile toplanacağını ve nihai görüntü keskinliğini doğrudan belirler.

## 4. Elektromanyetik Sönümleme ile Optik Soğurma Katsayısı İlişkisi

Elektromanyetik teoride, kayıplı bir ortama giren elektromanyetik dalganın elektrik alan genliği derinlikle sönümlenir:

```text
E(x) = E₀ · e^(-α_EMT · x)
```

Burada `α_EMT`, elektrik alan genliği için tanımlanan sönümleme katsayısıdır. Ancak optik sensör fiziğinde doğrudan elektrik alan genliğinden ziyade ışığın taşıdığı güç yoğunluğu, yani ışınım şiddeti (`intensity`, `I`) ile ilgilenilir. Poynting vektörünün büyüklüğü elektrik alan genliğinin karesiyle orantılıdır:

```text
I(x) ∝ |E(x)|² = |E₀|² · e^(-2α_EMT · x)
```

Optikte kullanılan soğurma katsayısı bu nedenle genlik sönümleme katsayısının iki katı olarak yazılır:

```text
α = 2α_EMT
```

Sonuç olarak optikte `α`, silisyum içindeki elektromanyetik kayıpların ışık şiddeti üzerindeki etkisini temsil eder.

## 5. Dalga Boyu (`λ`) ve `α` İlişkisi: Mavi Işık - Kırmızı Işık Karşılaştırması

Dalga boyu küçüldükçe foton enerjisi artar. Bu nedenle mavi ışık, kırmızı ışığa göre daha yüksek frekanslı ve daha yüksek enerjilidir. Görünür spektrum ve renk-dalga boyu ilişkisi için kaynak notu: `Munsell Color, Chemistry of Fireworks Colors`.

- Mavi ışık: `λ_mavi ≈ 450 nm`; dalga boyu küçüktür, frekansı ve enerjisi yüksektir.
- Kırmızı ışık: `λ_kırmızı ≈ 650 nm`; dalga boyu büyüktür, frekansı ve enerjisi daha düşüktür.

Silisyumun soğurma katsayısı `α(λ)`, dalga boyuna göre büyük ölçüde değişir:

| Dalga boyu | Yaklaşık soğurma katsayısı | Penetrasyon derinliği | Yorum |
| --- | --- | --- | --- |
| Mavi ışık - `450 nm` | `α_mavi ≈ 20.000 cm^-1` | `L_mavi = 1 / 20.000 cm^-1 ≈ 0.5 µm` | Çok sığ soğurulur; yüzey etkileri kritik hale gelir. |
| Kırmızı ışık - `650 nm` | `α_kırmızı ≈ 3.000 cm^-1` | `L_kırmızı = 1 / 3.000 cm^-1 ≈ 3.3 µm` | Daha derinde soğurulur; nötr bölge ve difüzyon etkileri önem kazanır. |

Bu karşılaştırmanın temel sonucu şudur: Enerjisi yüksek mavi ışık için silisyum çok daha güçlü bir soğurucu ortam gibi davranır. Kırmızı ışıkta ise silisyum daha az soğurucu, yani daha geçirgen davranır. Bu yüzden farklı dalga boyları, PPD içinde farklı derinliklerde elektron-delik çifti üretir.

## 6. Yük Taşıyıcı Dinamikleri: Drift ve Difüzyon

Foton soğurulduğunda bir elektron-delik çifti (`Electron-Hole Pair - EHP`) oluşur. Star tracker açısından kritik olan nokta, oluşan elektronun doğru pikselin `n`-kuyusunda toplanabilmesidir. Elektronun hareketini belirleyen iki temel mekanizma vardır: drift ve difüzyon.

### 6.1. Drift (Sürüklenme - Hızlı Mekanizma)

Drift, elektrik alan altındaki taşıyıcı hareketidir. PPD içindeki tüketim bölgesinde (`depletion region`), yük yoğunluğuna bağlı olarak güçlü bir elektrik alan oluşur. Bu durum Poisson denklemi ile ifade edilir:

```text
∇ · E = ρ / ε_Si
E_x(x) = - dV(x) / dx
```

Bu elektrik alan içine düşen elektronlar sürüklenme hızıyla hızla `n`-kuyusuna çekilir:

```text
v_d = μ_n E
```

Drift mekanizması hızlıdır ve nanosaniyeler mertebesinde gerçekleşebilir. Bu nedenle yıldız görüntüsündeki yük dağılımının doğru piksel çevresinde kalması bakımından tercih edilen taşıyıcı toplama mekanizmasıdır.

### 6.2. Difüzyon (Yayınım - Yavaş Mekanizma)

Elektrik alanın bulunmadığı nötr bölgelerde, örneğin `p`-substrate derinliklerinde, elektronlar rastgele termal hareketlerle yayılır. Bu hareket `Brownian motion` karakterindedir. Difüzyon akım yoğunluğu aşağıdaki gibi yazılır:

```text
J_n,diff = qD_n · dn/dx
```

Burada `D_n`, elektron difüzyon katsayısıdır.

Difüzyon, drift mekanizmasına göre daha yavaş ve daha kontrolsüzdür. Elektronun hangi piksele ulaşacağı yalnızca elektrik alan geometrisiyle değil, rastgele yayılma hareketiyle de belirlenir.

Not: Orijinal PDF bu bölümde dalga boyuna bağlı soğurulmayı gösteren bir şema içeriyor. Markdown sürümünde görsel yerine metinsel içerik korunmuştur.

## 7. Star Tracker İçin Neden Kritik?

Star tracker görüntüleme zincirinde amaç yalnızca yıldızdan gelen fotonları algılamak değildir. Asıl kritik hedef, yıldız görüntüsünün merkezini `centroid` hesabı ile piksel altı hassasiyette belirlemektir. Bu nedenle fotonun nerede soğurulduğu ve oluşan elektronun hangi yolla toplandığı doğrudan yönelim doğruluğunu etkiler.

Eğer foton çok derinde soğurulur ve elektrik alanın bulunmadığı nötr bölgede bir elektron üretirse, bu elektron `n`-kuyusuna drift ile değil difüzyonla ulaşmaya çalışır. Bu durum iki temel probleme yol açar:

1. `Charge sharing (yük paylaşımı)`: Elektron difüzyonla yayılırken komşu piksele sızabilir. Star tracker, yıldız merkezini piksel altı hassasiyetle hesaplamak için komşu piksellerdeki yük dağılımını kullanır. Elektronların rastgele biçimde yan piksellere yayılması centroid hesabını bozar.
2. `Yavaş tepki süresi`: Difüzyon yavaş bir süreçtir. Bu durum görüntüde `smear/lag` etkisine, yani yıldız izinin zamansal olarak uzamasına veya kuyruklanmasına neden olabilir.

## 8. İki Kritik Soğurulma Durumu

### 8.1. Aşırı Soğurulma: Yüzeyde Boğulma - Mavi Işık Etkisi

`α` katsayısı çok büyük olduğunda, özellikle mavi ve morötesi ışıkta, fotonlar silisyuma girer girmez soğurulabilir. Bu durumda foton, elektrik alanın etkili olduğu tüketim bölgesine ulaşamadan yüzeydeki ince `p+` tabakasında veya yüzey arayüzüne çok yakın bir bölgede enerjisini bırakır.

- Sorun: Yüzeydeki `SiO₂-Si` sınırında bulunan kristal kusurları ve tuzaklar, oluşan elektronları yakalayabilir. Bu olay `yüzey rekombinasyonu (surface recombination)` olarak değerlendirilir.
- Sonuç: Foton soğurulmuş olsa bile etkin elektriksel sinyal üretilemeyebilir. Kuantum verimliliği düşer.

### 8.2. Yetersiz Soğurulma: Derinlerde Kaybolma - Kırmızı/Kızılötesi Etkisi

`α` katsayısı çok küçük olduğunda, özellikle kırmızı ve kızılötesi bölgede, foton silisyum içinde daha uzun mesafe ilerler. Tüketim bölgesini geçtikten sonra arka taraftaki nötr `p`-substrate bölgesinde soğurulabilir.

- Sorun: Bu bölgede elektrik alan olmadığından elektronlar drift ile hızlıca toplanamaz. Rastgele difüzyonla hareket ederken rekombine olabilir veya komşu piksellere kaçabilir.
- Sonuç: Çözünürlük, hedef tespiti netliği ve `MTF` bozulur. Star tracker için centroid doğruluğu olumsuz etkilenir.

## 9. Mühendislik Çözümleri: BSI ve Deep Depletion

1. Mavi ışık için `BSI (Backside Illumination)`: Modern sensörlerde yapı ters çevrilerek ışık, metal yolların ve `p+` tabakasının bulunduğu ön yüzeyden değil, inceltilmiş arka yüzeyden sensöre alınır. Böylece mavi ışığın doğrudan tüketim bölgesine ulaşma ihtimali artar.
2. Kırmızı ışık için `deep depletion`: Silisyum daha az dop edilerek, yani yüksek dirençli silisyum (`high-resistivity silicon`) kullanılarak tüketim bölgesinin fiziksel genişliği `W` artırılır. Böylece depletion bölgesi daha derine uzanır ve kırmızı/kızılötesi fotonların etkin bölgede soğurulma ihtimali yükselir.

## 10. Kısa Sonuç

CMOS APS tabanlı star tracker sensörlerinde PPD yapısı, fotonla üretilen elektronların doğru pikselde, düşük gürültüyle ve hızlı biçimde toplanması için kritik öneme sahiptir. `p+` yüzey tabakası karanlık akımı azaltırken, gömülü `n`-kuyu elektronları yüzey tuzaklarından uzak bir bölgede toplar.

Silisyumun `indirect band gap` yapısı, foton soğurulmasını fonon yardımlı hale getirir ve soğurma derinliğini dalga boyuna güçlü biçimde bağımlı kılar. Mavi ışık yüzeye çok yakın soğurularak yüzey rekombinasyonu riskini artırırken, kırmızı/kızılötesi ışık daha derinde soğurularak difüzyon, charge sharing ve smear/lag risklerini gündeme getirir.

Bu nedenle star tracker mimarisinde sensör katman geometrisi, doping profili, depletion bölgesi derinliği, `BSI` yaklaşımı ve `deep depletion` tasarımı doğrudan yıldız merkezi hesaplaması, hedef tespiti netliği ve yönelim doğruluğu ile ilişkilidir.

## Kaynak Notu

Dalga boyu-renk ilişkisi için not edilen kaynak:

- Munsell Color, "Chemistry of Fireworks Colors"  
  https://munsell.com/color-blog/chemistry-fireworks-colors/
