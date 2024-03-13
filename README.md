# yzm208

# Giriş (Özet)
Sınıflandırma problemi (Classification) günümüzde makine öğrenmesinin temel bir problemlidir. Bir sınıflandırma probleminde, algoritmanın amacı sınıflarıyla birlikte verilen bir eğitim seti ile bir sınıflandırıcı oluşturmaktır. Genellikle verilen bir eğitim seti E, bir özellik vektörü (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>) ile temsil edilmektedir. Burada x<sub>i</sub>, özellik vektörü X<sub>i</sub>'nin değeridir. Diyelim ki C sınıflandırma değişkenini temsil etsin ve c sınıflandırma değişkeninin değerini temsil etsin. Bu çalışmada sadece 2 sınıf olduğu varsayılmaktadır: + (pozitif sınıf) veya - (negatif sınıf).

# Metot
## Naive Bayes
Sınıflandırıcı verilen örnek E'ye bir sınıf değeri atayan fonksiyondur. Bu çalışma için 3 model geliştirilecektir. Birinci model saf gaussian naive bayes kullanılarak oluşturulmuştur, ikinci model parametre optimizasyonu yapılmış naive bayestir, üçüncü model ise düzenlenmiş veri ile eğitilen naive bayestir. Naive bayes'in olasılık dağılımına göre verilen bir örnek E = (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>) için sınıfın c olma olasılığı:<br/>
P(C | x<sub>1</sub>, ..., x<sub>n</sub>) = (P(C) * P(x<sub>1</sub>, ..., x<sub>n</sub> | C)) / P(x<sub>1</sub>, ..., x<sub>n</sub>)<br/>
Verilen örnek E, c olarak sınıflandırılması için gerek ve yeter şart:<br/>
f<sub>b</sub>(E) = P(C = +| x<sub>1</sub>, ..., x<sub>n</sub>) / P(C = -| x<sub>1</sub>, ..., x<sub>n</sub>) >= 1<br/>
Burada f<sub>b</sub>(E) bayesian sınıflandırıcı olarak adlandırılır. Varsayın ki verilen örnek E'de bütün özellikler birbirinden bağımsız; yani,<br/>
P(E | C) = P(x<sub>1</sub>, ..., x<sub>n</sub> | C) = ∏<sup>n</sup><sub>i=1</sub> Px<sub>i</sub> | C)<br/>
Buna göre sınıflandırıcı:<br/>
f<sub>nb</sub>(E) = P(C = +) / P(C = -) * ∏<sup>n</sup><sub>i=1</sub> P(x<sub>i</sub> | C = +) / P(x<sub>i</sub> | C = -)<br/>
Burada f<sub>nb</sub>(E) fonksiyonu bayes sınıflandırıcısı veya naive bayes olarak adlandırılır.
## Gaussian Naive Bayes
Bu algoritma öncelikle verilen örnek E'nin (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>) bütün özelliklerini gaussian (normal) dağılımına dönüştürmektedir. Yani algoritma çalışırken özellik sayısı kadar gaussian dağılımı oluşturulmaktadır. Ardından verilen örnek E'nin hangi sınıfa ait olduğunu hesaplamak içinse önce bir P(C = +) ön değeri hesaplamaktadır. Bu ön değer herhangi bir yaklaşıklık olabilir. Örneğin; veri setinde 200 adet pozitif 150 adet negatif sınıf varsa, P(C = +) olasılığı 200 / 350 şeklinde hesaplanabilir. Aynı şekilde P(C = -)'de 150 / 350 şeklinde hesaplanır. Bunlara prior probability (önsel olasılık) denir. Sınıflandırıcı oluşmadan önce (deneyden önce) yapılabilecek en iyi varsayım olarak da geçer. Prior probability hesaplandıktan sonra verilen örnek E'nin pozitif sınıf ve negatif sınıf likelihood'ları hesaplanır. Bunlar örnek hakkında bir çıkarımdır ve daha önceden oluşturulan gaussian dağılımlarına göre hesaplanır. Örneğin 3 özelliği olan örnek E<sub>1</sub>'nin sınıfını manuel olarak hesaplayalım:<br/>
| Özellik | Özellik Değeri |
| --- | --- |
| Glikoz Değeri | 85 |
| BMI Değeri | 33.6 |
| İnsulin Değeri | 12 |<br/>

P(E | C) = P(x<sub>1</sub>, ..., x<sub>n</sub> | C) = P(C) * ∏<sup>n</sup><sub>i=1</sub> P(x<sub>i</sub> | C)'dir. Burada P(C) prior probability olup herhangi bir varsayım olabilir, şimdilik 0.6 varsayalım. Ardından likelihood'lar hesaplanır: P(x<sub>i</sub> | C). Bu değerde hesaplanan gaussian dağılımına göre bulunur. Dağılım fonksiyonunda x yerine 85 (Glikoz Değeri) girersek y değeri 0.004 olmaktadır. BMI değeri için 0.0001, insulin değeri için ise çok çok küçük bir değer çıkmaktadır. Bunları çarpıp formüle göre P(E | C) bulabiliriz. Ancak çok küçük değerlerle çarpım işlemi yapıldığı zaman bilgisayar zorlanmaktadır. Bilgisayarın bir sayıyı hafızada tutabilmesi için ancak belli bir küçüklükte olmalıdır, o değerden daha da küçük bir sayı tutmaya çalıştığında ise hata vermektedir. Bundan dolayı biz bu çarpımın logaritmasını alıyoruz. Logaritma içinde çarpım logaritmaların ayrı ayrı toplanması demektir. Bu işlemi tüm özellikler için yaptıktan sonra elde ettiğimiz değer diyelim P(x<sub>1</sub> | C = +) = -53 olsun. Aynı işlemleri negatif sınıf için yaparsak da diyelim ki P(x<sub>1</sub> | C = -) = -23 olsun. O zaman P(x<sub>1</sub> | C = -) > P(x<sub>1</sub> | C = +) olduğundan dolayı sınıflandırıcı sonuç olarak negatif (0) değerini verecektir. 

# Sonuçlar
Saf veri ile gaussian naive bayes eğittiğimiz zaman 

# Yorum
