# Star Tracker Sistemlerinde Baffle Elemaninin Islevi ve Tasarim Esaslari

Bu dosya, [`baffle_WO_vanes_rapor.pdf`](../pdf/baffle_WO_vanes_rapor.pdf) iceriginden Markdown formatina cevrilmis calisma metnidir.

## Not

- Kaynak belge: `pdf/baffle_WO_vanes_rapor.pdf`
- Amac: Raporu VS Code ve AI araclari tarafinda daha kolay okunabilir hale getirmek
- Donusum tipi: PDF'den duz metin/Markdown donusumu
- Durum: Ilk duzenlenmis surum

---

Star Tracker Sistemlerinde Baffle Elemanının
İşlevi ve Tasarım Esasları
Teknik Değerlendirme Raporu
Raporun amacı: Star tracker optik sistemlerinde kullanılan baffle elemanının temel
görevini, fiziksel çalışma prensibini, geometrik kabul açısı mantığını, yüzey optiği etkilerini ve sonraki aşamada incelenecek vane yapılarıyla ilişkisini özet ve teknik bir
çerçevede açıklamaktır .
Haziran 2026
1. Yönetici Özeti
Baffle, star tracker optik sistemlerinde optik eksen dışından gelen istenmeyen ışığı bastırmak için kullanılan mekanik-optik bir ışık kontrol yapısıdır . Temel görevi, yıldız görüntülerini oluşturacak faydalı ışığı optik sisteme kabul ederken; Güneş, Ay, Dünya yansıması,
uzay aracı yüzeyleri veya laboratuvar test kaynaklarından gelen zararlı ışığın lens ve sensöre ulaşmasını sınırlamaktır .
Star tracker sistemlerinde yıldız sinyali çok zayıftır . Bu nedenle eksen dışı parlak kaynaklardan gelen düşük seviyeli bir saçılma dahi arka plan seviyesini yükseltebilir , yıldız kontrastını azaltabilir , sensörde doygunluk oluşturabilir veya ölçüm doğruluğunu düşürebilir .
Baffle bu riski, geometrik gölgeleme ve yüzey soğurması birlikte çalışacak şekilde azaltır .
Teknik olarak baffle performansı iki ana unsurun birleşimiyle değerlendirilir: uygun iç geometri ve düşük yansıtıcılı yüzey optiği. Geometri, hangi açılardan gelen ışığın optik yola
ulaşabileceğini belirler . Yüzey optiği ise baffle iç duvarına çarpan ışığın ne kadarının yansıyacağını, soğurulacağını veya saçılacağını belirler .
Baffle Performansı ≈ Geometrik Kontrol + Yüzey Optiği
2. Baffle Elemanının Konumu ve Görevi
Baffle, star tracker cihazının gökyüzüne bakan ön kısmında, lens grubundan önce yer alır .
Tipik bir optik dizilim şu sırayı izler:
Uzay / Gökyüzü → Baffle Girişi → Baffle İç Hacmi → Lens Grubu → Filtre veya Window →
Sensör → Elektronik Birimler
Bu konumlandırma sayesinde istenmeyen ışık, lens grubuna ve sensöre ulaşmadan önce
kontrol altına alınır . Baffle çoğunlukla silindirik veya konik gövdeli, iç yüzeyi siyah ve mat
kaplanmış bir yapı olarak tasarlanır . Hassas sistemlerde iç yüzeyde halka, basamak, dudak
veya vane benzeri yapılar bulunabilir .
Baffle’ın optik sistemdeki esas işlevleri şunlardır:
• Faydalı görüş alanı içindeki yıldız ışığını optik sisteme kabul etmek,
• Görüş alanı dışından gelen parlak kaynak ışığını bastırmak,
• Lensin doğrudan görebileceği eksen dışı ışın yollarını sınırlamak,
• İç yüzey yansımalarıyla oluşabilecek dolaylı ışık yollarını zayıflatmak,
• Sensörde arka plan parlaklığı ve doygunluk riskini azaltmak.
3. Stray Light Problemi
Baffle tasarımının temel gerekçesi stray light kontrolüdür . Stray light, hedeflenen yıldız görüntüsüne ait olmayan fakat optik sisteme girerek ölçümü bozan ışıktır . Bu ışık iki ana yolla
sisteme etki eder .
3.1. Doğrudan Eksen Dışı Işık
Eksen dışı bir parlak kaynak, baffle geometrisi tarafından yeterince sınırlandırılmazsa lensi
doğrudan görebilir . Bu durumda ışık doğrudan sensör düzlemine taşınabilir . Özellikle Güneş ve Ay gibi yüksek parlaklıklı kaynaklar , küçük bir kaçakla dahi yıldız tespitini olumsuz
etkileyebilir .
3.2. Yansıma ve Saçılma Kaynaklı Dolaylı Işık
Işık doğrudan lensi görmese bile baffle iç yüzeyine çarpıp yansıyabilir veya saçılabilir . Bu
ışık tek veya çoklu sekmelerden sonra lens yönüne ulaşabilir . Bu nedenle baffle tasarımında
doğrudan yolun yanında potansiyel yansıma yolları da kontrol edilmelidir .
Bu noktada line of sight kavramı önemlidir . İstenmeyen ışık için giriş açıklığından bakıldığında lensin veya sensörün doğrudan görülmesi sınırlandırılır . Daha ileri tasarımda, bir
veya birkaç yansımadan sonra oluşabilecek görüş yolları da incelenir .
4. Açısal Filtreleme ve Görüş Alanı İlişkisi
Baffle, ışığı geliş açısına göre seçen bir yapı gibi davranır . Referans doğrultu optik eksendir .
Optik eksene yakın gelen ışınlar küçük açılı; optik eksenden uzaklaşan ışınlar büyük açılı
olarak değerlendirilir .
Star tracker sisteminde kabul edilen açı aralığı, sistemin görüş alanı (FOV), lens özellikleri, sensör boyutu ve görev gereksinimleriyle belirlenir . Bu nedenle baffle, optik eksendeki
ışınla birlikte faydalı görüş alanı içindeki tüm yıldız ışığını geçirecek şekilde tasarlanır . Görüş alanı dışındaki parlak kaynaklardan gelen ışık ise bastırılır .
5. Geometrik Kabul Açısı
Basit bir silindirik baffle modeli, kabul açısı kavramını açıklamak için yeterli bir ilk yaklaşımdır . İç yarıçapı𝑟, uzunluğu 𝐿 olan düz bir tüpte, ışığın duvara çarpmadan ilerleyebileceği
yaklaşık sınır açı aşağıdaki şekilde ifade edilir:
𝜃crit = tan−1( 𝑟
𝐿 )
Burada 𝜃crit, baffle’ın yaklaşık geometrik kabul açısıdır . Gelen ışın açısı bu değerin altında
kaldığında ışın doğrudan optik yol boyunca ilerleyebilir . Bu değerin üzerindeki açılarda ışın
baffle duvarına çarpar .
𝜃 < 𝜃 crit ⇒ doğrudan geçiş olası
𝜃 > 𝜃 crit ⇒ duvarla kesilme beklenir
Örnek olarak, 𝑟 = 10 mm ve 𝐿 = 50 mm için:
𝜃crit = tan−1( 10
50 ) = tan−1(0.2) ≈ 11.3 ∘
Bu örnekte optik eksenden yaklaşık 11.3∘ içinde gelen ışık doğrudan geçiş imkanı bulabilir .
Daha büyük açılı ışınların baffle duvarına çarpması beklenir . Gerçek sistemlerde bu hesap
lens açıklığı, sensör boyutu, odak uzaklığı, FOV , vane geometrisi ve yüzey saçılma karakteriyle birlikte değerlendirilir .
6. Küçük Açı Yaklaşımı ve Kullanım Sınırı
Küçük açı kavramı, matematiksel yaklaşım ve optik kabul açısı bakımından ayrı değerlendirilmelidir . Matematikte küçük açı, trigonometrik fonksiyonların radyan cinsinden yaklaşık
ifade edilebildiği bölgedir:
sin 𝜃 ≈ 𝜃, tan 𝜃 ≈ 𝜃, cos 𝜃 ≈ 1 − 𝜃2
2
Bu yaklaşımda 𝜃 radyan cinsindendir . Örnek dönüşümler:
1∘ ≈ 0.01745 rad, 5 ∘ ≈ 0.0873 rad, 10 ∘ ≈ 0.1745 rad
Baffle tasarımında küçük veya büyük açı değerlendirmesi, çoğu zaman sistemin kabul açısı,
FOV değeri ve dışlama gereksinimleriyle ilişkilidir . Dolayısıyla pratik sınır , başta sistem geometrisi olmak üzere görev gereksinimleriyle belirlenir .
7. Yüzey Optiği: Yansıma, Soğurma ve Geçirme
Baffle’ın iç yüzeyine ulaşan ışık için enerji dengesi şu şekilde yazılır:
𝑅 + 𝐴 + 𝑇 = 1
Bu ifadede 𝑅 yansıyan enerji oranını, 𝐴 soğurulan enerji oranını, 𝑇 ise geçen enerji oranını
gösterir . Baffle iç yüzeyi için hedeflenen davranış aşağıdaki gibidir:
𝑇 ≈ 0, 𝑅 → küçük, 𝐴 → büyük
Bu nedenle baffle iç yüzeyinde mat siyah, düşük reflektanslı ve yüksek soğuruculu kaplamalar kullanılır . Görsel koyuluk tek başına performans ölçütü yerine, ilgili dalga boyu aralığındaki optik davranışla birlikte değerlendirilir . İlgili dalga boyu aralığında reflektans, saçılma
karakteri, speküler yansıma oranı ve kaplama kararlılığı birlikte değerlendirilir .
Soğurma, gelen elektromanyetik enerjinin malzeme içinde iç enerjiye dönüşmesidir . Işığın
elektrik alanı yüzeydeki elektronlar ve atomik yapı ile etkileşir . Bu enerji mikroskobik düzeyde uyarımlara ve titreşimlere aktarılır; makroskobik karşılığı ısı oluşumudur .
8. İç Geometri: Basamaklı ve Halkalı Yapılar
Düz ve uzun bir iç yüzey, belirli koşullarda istenmeyen ışık için düzenli yansıma yolu oluşturabilir . Özellikle speküler bileşeni yüksek yüzeylerde, eksen dışı bir ışın tek bir sekme ile
lens yönüne ilerleyebilir .
Basamaklı, halkalı veya dudaklı iç yapılar bu riski azaltmak için kullanılır . Bu yapılar:
• Doğrudan görüş çizgisini parçalar ,
• Tek sekmeli lens görüşünü zorlaştırır ,
• Işığı birden fazla yüzey etkileşimine yönlendirir ,
• Her etkileşimde enerji kaybı ve soğurma ihtimalini artırır ,
• Aynasal ve düzenli yansıma yollarını bozar .
Bu geometrik yaklaşım, sonraki aşamada incelenecek vane tasarımının da temel mantığını
oluşturur . Vane yapıları; konum, yükseklik, aralık, açı ve yüzey kaplaması bakımından ayrıca değerlendirilmelidir .
9. Malzeme ve Kaplama Değerlendirmesi
Baffle gövdesi metal, hafif alaşım, kompozit veya karbon fiber destekli malzemelerden üretilebilir . Malzeme seçimi; ağırlık, rijitlik, termal kararlılık, üretilebilirlik ve görev ortamı
bakımından önem taşır . Optik performans açısından belirleyici unsur iç yüzeyin kaplama
ve mikroyapı karakteridir .
Değerlendirilmesi gereken başlıca yüzey özellikleri şunlardır:
• İlgili dalga boylarında düşük reflektans,
• Düşük speküler yansıma,
• Yüksek soğurma,
• Kontrollü saçılma davranışı,
• Uzay ortamında kaplama kararlılığı,
• Termal çevrimlere ve mekanik koşullara dayanım.
Parlak ve düzgün yüzeyler stray light açısından risklidir . Mat, düşük yansıtıcılı ve optik olarak kararlı yüzeyler tercih edilir .
10. Tasarım Kriterleri
Bir star tracker baffle tasarımında aşağıdaki kriterler birlikte ele alınmalıdır:
1. Faydalı görüş alanı ve hedef FOV ,
2. Lens açıklığı ve odak uzaklığı,
3. Sensör boyutu ve yıldız görüntüleme gereksinimi,
4. Güneş, Ay ve Dünya yansıması kaynaklı dışlama açıları,
5. Stray light toleransı,
6. Baffle uzunluğu, çapı ve iç profili,
7. İç yüzey kaplaması ve BRDF davranışı,
8. Line of sight kesimi,
9. Tekli ve çoklu yansıma yolları,
10. Vane yerleşimi ve üretim toleransları.
Profesyonel tasarımda ray tracing analizleri, BRDF verileri, exclusion angle gereksinimleri
ve PST eğrileri kullanılarak baffle performansı doğrulanır . Bu analizler , basit geometrik kabul açısı hesabını daha gerçekçi hale getirir .
11. Sonuç
Baffle, star tracker sistemlerinde yıldız ölçüm doğruluğunu koruyan kritik bir optik-mekanik
elemandır . Faydalı ışık ile istenmeyen eksen dışı ışık arasındaki ayrım, baffle geometrisi ve
iç yüzey optiği üzerinden sağlanır . Temel çalışma prensibi, geometrik gölgeleme ile doğrudan ışık yollarını sınırlamak ve düşük reflektanslı yüzeylerle yansıma kaynaklı kaçakları
bastırmaktır .
Basit bir baffle yapısı dahi belirli ölçüde yan ışık baskısı sağlayabilir . Star tracker gibi zayıf
yıldız sinyaliyle çalışan hassas sistemlerde nihai performans; iç geometri, yüzey kaplaması,
line of sight kontrolü, yansıma analizi ve vane yapılarının birlikte değerlendirilmesiyle elde
edilir .
Bu çerçevede baffle, ölçüm kalitesini doğrudan etkileyen ve tasarım gereksinimlerine göre
optimize edilmesi gereken bir ışık kontrol sistemi olarak ele alınmalıdır .
Sayfa 5 / 5
Şekil 1. Baffle kesitinde basamaklı iç yapı ve kesikli ışın yolları (temsili)
Giriş
açıklığı
basamaklı / halkalı iç profil
kesikli yollar: eksen dışı ışık duvara yönlenir
faydalı ışın
Lens Sensör
duvar / vane kesimi
