# Bulaşıcılığı Arttıran Koronavirüs SARS CoV2 Mutasyonlarının Tahmini
## Özet
2019 yılında ortaya çıkan ve 223 ülkeyi etkisi altında alan COVID-19 pandemisi, günümüze (Şubat 2021) kadar 110 milyon vakaya ve 2.5 milyon ölüme sebep olmuştur (WHO, 2021). COVID-19 pandemisi, SARS-CoV-2 virüsünün ve bu virüse avantaj sağlayan varyantlarının hızla yayılması sonucunda bu bulaşıcılık seviyesine erişmiştir. Bahsi geçen avantaj sağlayıcı varyantlar, özellikle tek amino asit (nokta) bazında görülen mutasyonlar yoluyla meydana gelmiştir. Bu nokta mutasyonları, SARS-CoV-2’nin yapısında değişikliklere yol açabildiği gibi, virüsün insan konağına girmek için ilk basamak olarak kullandığı ACE2 proteini ile etkileşim verimini de etkileyebilmektedir. ACE2 ile bağlanmayı etkileyen N501Y ve E484K mutasyonları yaygın olarak İngiltere’de, Güney Afrika’da ve Brezilya’da gözlemlenmiş ve tüm dünyada endişeye sebep olmuştur. Bu olgudan yola çıkarak tasarladığımız projede, N501Y ve E484K kadar etkin olabilecek ve bulaşıcılığının yüksek olması nedeniyle tehlike yaratabilecek SARS-CoV-2 mutasyonlarının tahmin edilmesi amaçlandı. Bu hedef doğrultusunda, özgün bir çalışma olarak, SARS-CoV-2 ve ACE2 bağlanma ve stabilitesine ait deneysel veriler farklı aminoasit özellikleri ile ilişkilendirilip, makine öğrenmesi ve hesaplamalı biyoloji tekniklerine entegre ederek, algoritmalarda yapılan analizler sonucunda _**N501M, Q414A, N354K, Q498H, N460K, N501W**_ mutasyonlarının, koronavirüsünün yayılmasında tehlikeli olma ihtimallerinin yüksek olduğu belirlendi. Şu anda yaygın olan varyantlardan birinde görülen 501. pozisyon mutasyonlarına özellikle dikkat edilmesi gerektiğini, bu pozisyonunun listelerde tekrar etmesi üzerine özellikle önermekteyiz. Özellikle sekanslama sırasında karşılaşılması durumunda bu mutasyonların yayılımının engellenmesi konusunda büyük hassasiyet gösterilmeli ve gerekli sağlık tedbirleri alınmalıdır. Makine öğrenmesi ve hesaplamalı biyoloji ışığında yapılan bu araştırmanın sonuçları COVID-19 pandemisi konusunda ileriki çalışmalara alt yapı sağlayacak ve virüsle olan savaşta bilim insanlarına yol gösterecektir. 

## Amaç
Projemiz kapsamında, hangi SARS-CoV-2 mutasyonlarının virüsün bulaşıcılığını arttıracağını, makine öğrenmesi ve hesaplamalı biyoloji teknikleri kullanarak tahmin etmeyi amaçladık. Bu amaç doğrultusunda sırasıyla şu basamakları takip ettik:
 * SARS-CoV-2 ile hedef proteini ACE2 arasındaki etkileşimini etkileyen mutasyon bilgilerinin literatürden toplanması,
 * SARS-CoV-2 mutasyonlarının etkisini biyokimyasal olarak karakterize edecek amino asit değişim özelliklerinin literatürden elde edilmesi ve işlenmesi,
 * İstelenen bilgilerdeki örüntüyü ortaya çıkartmak için k-ortalama ve beklenti maksimizasyonu algoritmalarını kullanarak, hangi SARS-CoV-2 mutasyonlarının N501Y ve E484K mutasyonlarıyla benzer etkiye sahip olabileceğinin araştırılması,
 * Aynı sınıfta olan mutasyonların SARS-CoV-2 ile ACE2 etkileşimi çerçevesinde değerlendirilmesi.

## Sonuçlar
Mutasyon kaynaklı S-protein stabilite ve ACE2’ye bağlanma değişimi deney verileri literatürden sağlanarak kendi yazdığımız python kodunu ile bu veri setinin içinde, S-proteinin ACE2’ye daha iyi bağlanmasını sağlayan veya bağlanmasını olumsuz etkilemeyen 586 deneysel mutasyon verisini ayıklandı. Daha sonra, bu mutasyonlarda etkili aminoasit özellikleri olan Hidropati, Polarite, Hacim, Moleküler Ağırlık, Aminoasit Yapısındaki Halka Sayısı, Oksijen Sayısı, Hidrojen Sayısı ve Çift Bağ Sayısı Değişimi cinsinden kodlandı ve deney verileri ile ilişkilendirildi. 586 adet mutasyon içeren ve N501Y ile E484K verilerini kapsayan bu set, iki farklı makine öğrenmesi gruplama algoritmasına tanıtıldı. Bundan sonra, farklı grup (küme) sayıları için, hangi mutasyonların N501Y ve E484K mutasyonları ile aynı kümeye düşeceği araştırıldı. Bu amaç kapsamında makine öğrenmesi için yaygın olarak kullanılan Weka programı aracılığıyla, denediğimiz tüm kümeleme algoritmaları içinden en tutarlı sonuçları veren K-ortalama (k-means) kümeleme ve EM (Expectation Maximization) algoritmalarını kullanıldı. Bu kapsamda yapılan analizler sonucunda;
* K-ortalama kümeleme algoritması ile yapılan analizler sonucunda k=10 için hesaplanan 30 elemanlı 9. kümeye bakıldığında, stabilitesi en yüksek ilk beş mutasyon **N501M, Q414A, Q498H, N460K, N501W** (stabilitesi en çoktan en aza göre sıralanmıştır) olarak belirlendi. Bu mutasyonlar, K-ortalama kümeleme tarafından önerilen en tehlikeli beş mutasyon olarak belirlendi. Bu mutasyonlarda 501 pozisyonunun iki kere listelenmiş olması bu pozisyonda meydana gelebilecek mutasyonlar konusunda dikkatli olunması gerektiğini göstermektedir.
* Beklenti maksimizasyonu kümeleme algoritması ile yapılan analizler sonucunda k=10 için hesaplanan 46 elemanlı 8. kümeye bakıldığında, stabilitesi en yüksek ilk beş mutasyon N501M, N354K, Q498H, N460K, N501W (stabilitesi en çoktan en aza göre sıralanmıştır) olarak belirlendi. Yine bu algoritmada da 501 pozisyonuna ait aynı mutasyonlar en tehlikeli beş mutasyon listesinde seçildi.
* Her iki algoritmadan elde edilen kümelerin analizi sonucunda çıkan en tehlikeli beş mutasyon listesinde ortak mutasyonların olduğu görülmektedir. Bu ortak mutasyonların da değerlendirilmesi ile uzlaşmalı olarak **N501M, Q414A, N354K, Q498H, N460K, N501W** altı adet mutasyonun, koronavirüsünün yayılmasında tehlikeli etkileri olma ihtimali yüksek mutasyonlar olarak belirlendi. 
* Şu anda yaygın olan varyantlardan birinde görülen 501. pozisyon mutasyonuna özellikle dikkat edilmesi gerektiğini, bu listede 501 pozisyonunun tekrar etmesi üzerine özellikle önermekteyiz.
### K-means kümeleme algoritmasının sonuçları
| Cluster Sayısı | E484K'nin bulunduğu cluster | N501Y'nin bulunduğu cluster | E484K'nin bulunduğu cluster'daki eleman sayısı | N501Y'nin bulunduğu cluster'daki eleman sayısı |
|----------------|-----------------------------|-----------------------------|------------------------------------------------|------------------------------------------------|
| 2              | 1                           | 1                           | 445                                            | 445                                            |
| 3              | 1                           | 1                           | 299                                            | 299                                            |
| 4              | 3                           | 3                           | 164                                            | 164                                            |
| 5              | 3                           | 3                           | 164                                            | 164                                            |
| 6              | 5                           | 3                           | 118                                            | 66                                             |
| 7              | 5                           | 3                           | 119                                            | 65                                             |
| 8              | 1                           | 1                           | 57                                             | 57                                             |
| 9              | 8                           | 8                           | 56                                             | 56                                             |
| 10             | 9                           | 9                           | 30                                             | 30                                             |
| 11             | 9                           | 9                           | 30                                             | 30                                             |
| 12             | 9                           | 9                           | 29                                             | 29                                             |

## Kullandığımız Dosyalar
### [Deneysel Veriseti](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/Deneysel_veriseti.csv)
SARS-CoV-2’nin S-proteininindeki Hedef Tanıma Modülü (HTM) bölgesindeki olası tüm nokta mutasyonların ACE2 proteinine bağlanması üzerindeki etkilerini gösteren deneysel veriseti.
### [Özellikler](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/Ozellikler.csv)
Her bir aminoaside ait hidropati indeksi ve moleküler kütleyi gösteren veriseti. Kullandığımız verisetlerini oluştururken buradaki özelliklerden yararlandık.
### [veriduzenleme.py](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriduzenleme.py)
Varolan bazı verisetlerinden aldığımız veriyi bu kodla birleştirip ve düzenleyip verisetlerimizi oluşturduk.
### [Veriseti](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriseti.csv)
Kodumuzdaki veriyial() fonksiyonu ile oluşturduğumuz, hedef tanıma modülü'ndeki bütün mutasyonları ve bu mutasyonların hidropati farkı, moleküler kütle farkı, bağlanma ortalaması, ekspresyon ortalaması, polarite farkı ve hacim farkı özelliklerini bulunduran veriseti. Farkları hesaplarken mutant aminoaside ait olan özelliği vahşitip aminoasidinden çıkardık.
### [Veriseti Bağlanma Sıfır ve Üstü](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriseti_baglanma_sifir_ve_ustu)
[veriseti](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriseti.csv) dosyasındaki bağlanma afinitesi (bind_avg) değeri sıfıra eşit veya sıfırdan büyük olan mutasyonları içermektedir. Bu verisetini oluşturmak için kodumuzdaki baglanmasifirveustu() fonksiyonu ile bağlanma değeri sıfıra eşit olan veya sıfırdan büyük olan mutasyonları seçtik.
### [Veriseti Yeni Özellikler](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriseti_yeni_ozellikler) 
[veriseti](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriseti.csv) dosyasına kodumuzdaki yeniozellikekle() fonksiyonuyla halka sayısı farkı, hidrojen atomu sayısı farkı, oksijen atomu sayısı farkı, çift bağ sayısı farkı özelliklerini ekledik.
### [Veriseti Yeni Özellikler Bağlanma Sıfır ve Üstü](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/Veriseti_Yeni_Ozellikler_Baglanma_Sifir_ve_Ustu.csv)
[Veriseti Yeni Özellikler](https://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/veriseti_yeni_ozellikler) dosyasındaki bağlanma değeri (bind_avg) sıfır ve üstü olan mutasyonları seçtiğimiz veriseti. Bu verisetini oluşturmak için baglanmasıfırveustu() fonksiyonunu kullandık.

# 2.Analiz
2.Analizde mutasyon yerine interaksiyonları inceledik. Star ve Arkadaşlarının oluşturmuş olduğu RBD-ACE2 ikili interaksiyon verisi Python kodunda işleyerek çoklu interaksiyon verisi haline getirdik. Bu analizde probleme farklı bir açıdan yaklaşmış olup, sadece RBD'yi değil, RBD ve ACE2'yi beraber inceleyerek daha bütünsel bir analiz yapmış olduk.  

## K-Means Analiz Grafiği
| Küme Sayısı | Küme 0 Eleman Sayısı          | Küme 1 Eleman Sayısı  | Küme 2 Eleman Sayısı | Küme 3 Eleman Sayısı  | Küme 4 Eleman Sayısı | Küme 5 Eleman Sayısı | Küme 6 Eleman Sayısı |
|-------------|-------------------------------|-----------------------|----------------------|-----------------------|----------------------|----------------------|----------------------|
| 2           | 11(%52, K417 ve K484 burada)  | 10 (%48, Y501 burada) | 0                    | 0                     | 0                    | 0                    | 0                    |
| 3           | 7 (%33,  K417 ve K484 burada) | 6 (%29)               | 8 (%38, Y501 burada) | 0                     | 0                    | 0                    | 0                    |
| 4           | 5 (%24, 484K burada)          | 3 (%14)               | 8 (%38, 501Y burada) | 8 (%38, 501Y burada)  | 0                    | 0                    | 0                    |
| 5           | 3 ( %14, K484 burada)         | 5 (%24)               | 2 (%10)              | 3 (%14, K417 burada)  | 8 (%38, Y501 burada) | 0                    | 0                    |
| 6           | 3 (% 14, 484K burada)         | 5 (%24)               | 2 (%10)              | 3 (%14, K417 burada)  | 4 (%19)              | 4 (%19, 501Y burada) | 0                    |
| 7           | 3 (% 14, K484 burada)         | 5 (%24)               | 2 (%10)              | 2 (%10)               | 4 (%19)              | 4 (%19, 501Y burada) | 1 (%5, K417 burada)  |

## Dosyalar
[ACE2-RBD Kontacthttps://github.com/BiyoinformatikProje/Bulasiciligi-Arttiran-Koronavirus-SARS-CoV-2-Mutasyonlarinin-Tahmini/blob/main/ACE2-RBD_contact_details.txt

## Sonuçlar 
Bu analizimiz sonucunda, 
