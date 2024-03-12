# yzm208

# Giriş (Özet)
Sınıflandırma problemi (Classification) günümüzde makine öğrenmesinin temel bir problemlidir. Bir sınıflandırma probleminde, algoritmanın amacı sınıflarıyla birlikte verilen bir eğitim seti ile bir sınıflandırıcı oluşturmaktır. Genellikle verilen bir eğitim seti E, bir özellik vektörü (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>) ile temsil edilmektedir. Burada x<sub>i</sub>, özellik vektörü X<sub>i</sub>'nin değeridir. Diyelim ki C sınıflandırma değişkenini temsil etsin ve c sınıflandırma değişkeninin değerini temsil etsin. Bu çalışmada sadece 2 sınıf olduğu varsayılmaktadır: + (pozitif sınıf) veya - (negatif sınıf).

# Metot
Sınıflandırıcı verilen örnek E'ye bir sınıf değeri atayan fonksiyondur. Bu çalışma için 3 model geliştirilecektir. Birinci model saf gaussian naive bayes kullanılarak oluşturulmuştur, ikinci model parametre optimizasyonu yapılmış naive bayestir, üçüncü model ise düzenlenmiş veri ile eğitilen naive bayestir. Naive bayes'in olasılık dağılımına göre verilen bir örnek E = (x<sub>1</sub>, x<sub>2</sub>, ..., x<sub>n</sub>) için sınıfın c olma olasılığı:<br/>
P(C | x_1, ..., x_n) = (P(C) * P(x_1, ..., x_n | C)) / P(x_1, ..., x_n)<br/>
Verilen örnek E, c olarak sınıflandırılması için gerek ve yeter şart:<br/>
f<sub>b</sub>(E) = P(C = +| x_1, ..., x_n) / P(C = -| x_1, ..., x_n) >= 1<br/>
Burada f<sub>b</sub>(E) bayesian sınıflandırıcı olarak adlandırılır. Varsayın ki verilen örnek E'de bütün özellikler birbirinden bağımsız; yani,<br/>
P(E | C) = P(x_1, ..., x_n | C) = ∏<sup>n</sup><sub>i=1</sub> P(x_i | C)<br/>
Buna göre sınıflandırıcı:<br/>
f<sub>nb</sub>(E) = P(C = +) / P(C = -) * ∏<sup>n</sup><sub>i=1</sub> P(x_i | C = +) / P(x_i | C = -)<br/>
Burada f<sub>nb</sub>(E) fonksiyonu bayes sınıflandırıcısı veya naive bayes olarak adlandırılır.<br/>
![alt text](https://www.researchgate.net/publication/283161090/figure/fig1/AS:648613512364033@1531652920537/A-typical-Naive-Bayes-network-diagram.png)

# Sonuçlar

# Yorum
