# MachineLearningCrashCourse
This repo consists of the topics I hold about Machine Learning Crash Course

Framing : 
Supervised Machine Learning’te label ve features önemlidir. 
Machine Learning : daha önce hiç görülmemiş veriler hakkında yararlı tahminler üretmek için girdiyi nasıl birleştireceğini gösterir. 
Terminolojisi;
•	Labels : tahmin edilen şeylerdir. Etiketlerdir. Y, linear regression (basit doğrusal regresyon değişkeni)
•	Features : bir girdi değişkenidir. x1, x2, x3 … xn.
Model eğitimi için etiketleri kullanırız. Etiketlerle modeli eğittikten sonra, etiketsiz örnekleri de etiketlemek için tahmin yapılır.
•	Models : model, özellikler ve etiketler arasındaki ilişkiyi tanımlar. 
•	Train (Eğitim) : modelin oluşturulması veya öğretilmesi anlamına gelir. Model, etiketli örnekleri gösterir. 
•	Çıkarım : eğitilmiş modelin etiketlenmemiş örneklere uygulanmasıdır.
Yararlı tahminler için eğitimli modelleri kullanırız. 
Regression ve Sınıflandırma Karşılaştırılması : 
•	Regression modeli, sürekli değerleri öngörür (Ör: fiyat bilgisi, tıklama olasılığı)
•	Sınıflandırma modeli, ayrık değerleri öngörür (Ör: spam mı değil mi?, kedi mi fare mi?)











Reducing Loss : 
 
Modelin eğitimide, modelin kaybını azaltmak için bir yola ihtiyaç vardır. 
 An iterative approach to training a model : Model girdi ile bir veya daha fazla özelliği alır ve çıktı olarak bir tahmin (y) değeri dönderir. 
 
Başlangıç değerleri b = 0 ve w = 0’dır. x = 10 olduğu bilinirse formülde yerine konulduğunda y = 0’dır. 
Bir makine öğrenimi modeli, ağırlıklar (w) ve bias (b) için ilk tahminden başlayarak ve mümkün olan en düşük kayıp ile ağırlıkları (w) ve bias (b) öğrenene kadar bu tahminleri tekrarlı bir şekilde ayarlayarak eğitir. 
Gradient Descent (Dereceli İniş) : 
 
Eğrinin sıfır olduğu tek bir yer var o da kayıp fonksiyonun yakınsadığı yerdir. The gradient descent algoritması başlangıç noktasındaki kayıp eğrisinin gradyanını hesaplar. Kaybın eğimi, eğrinin türevini (eğimi)’dir. 
Birden fazla ağırlık olduğunda, gradian ağırlıklara göre kısmi türevlerin bir vektörüdür. Kısacası, Gradient ağırlıkların kısmi türevini tutan bir vektördür. 
Gradient daime Loss (kayıp) fonksiyonundaki en dik artış yönüdür (yön ve büyüklük önemlidir).
Learning Rate : Gradient vektörü hem bir yöne hem de bir büyüklüğe sahiptir. Öğrenme hızı adım sayısı olarak bilinebilir. Küçük bir öğrenme oranı seçilirse, öğrenme çok uzun sürebilir. Çok büyük bir oranda yanlış öğrenmeyi tetikleyebilir. Goldilocks öğrenme oranı, kayıp fonksiyonun ne kadar düz olduğu ile ilgilidir.
Stochastic Gradient Descent (Stokastik Dereceli İniş) : Tek bir yinelemede hesaplamak için kullandığınız toplam örnek sayısıdır. Çok büyük bir grup, tek bir yinelemenin bile hesaplanması çok uzun zaman alabilir. Belli bir kesim parti veriler çok büyük parti verilere oranla daha sağlıklı sonuçlar verebilir. 
Stokastik, yenileme başına sadece tek bir örnek kullanır. 
Batch Size (Yığın boyutu) : Modelin eğitilmesi aşamasında aynı anda kaç adet verinin işleneceği anlamına gelir.
Mini Batch Size : Birden fazla girdinin parçalar halinde işlenmesi “mini-batch” olarak adlandırılmaktadır. Model tasarlanırken mini-batch parametresi olarak belirlenen değer; modelin aynı anda kaç veriyi işleyeceği anlamına gelmektedir.
Hiperparametreler, programcıların makine öğrenme algoritmalarında ayarladığı parametrelerdir. Çok küçük bir öğrenme oranı seçerseniz, öğrenme çok uzun sürecektir. 
Learning Rate (LR : Öğrenme Hızı) : Düşük bir oran verilmesi işe yarar.
Training Loss (TL) : Eğitim hatası sıfıra yavaşça yaklaşmalı. Eğer yaklaşmazsa daha fazla epoch kullanılmalıdır. 
•	TL düşük, LR yüksek olmalıdır (Zıt yönde)
•	TL hızlıca artarsa, LR azaltılmaldır.
•	Epochs ve Batch Size yüksekse, LR azaltılmalıdır.
•	Önce büyük ölçek Batch Size denenmelidir, sonrasında eğitim kaybı bozuluna kadar batch size’I azaltılır. 
•	Büyük boy veri seti için, batch size azaltılmalıdır (memory düşünülmeledir)

Correlation Matrix : her bir özelliğin ham değerlerinin diğer özelliklerin ham değerleriyle nasıl ilişkisi olduğunu gösterir. 
•	1.0 : mükemmel pozitif korelasyon (bir özellik yükseldiğinde diğer özellikte yükselir)
•	-1.0 : mükemmel negative korelasyon (bir özellik yükselirken diğer özellik düşer)
•	0.0 : korelasyon yok (doğrusal ilişkili değildir.) 
Bir korelasyon değerinin mutlak değeri yüksekse tahmin gücüde yüksektir. Örneğin -0.8 lik bir değer -0.2 lik bir değerden çok daha fazla öngörme gücü vardır.
Generalization : 
Bir overfit modeli, eğitim sırasında düşük bir kayıt olur. Ancak yeni verileri öngören kötü bir iş çıkarır. 
Overfitting (Aşırı Uyum) : Bir modeli gereğinden fazla karmaşık hale getirmektir. 
ML temel prensibi, verilerin uyumu ve olabildiğince basitleştirilmesi gerekir. 
ML amacı : (gizli) gerçek olasılık dağılımından alınan yeni verileri iyi tahmin etmektir. 
Generalization tam olarak;
•	Modelin karmaşıklığı 
•	Modelin eğitim verileri üzerindeki performansı
Dataset ikiye ayrılır; training set (eğitim için kullanılan set) ve test set (test edilecek seti)
Varsayımlar : örnekler birbirini etkilememeli (rastgelelik esas alınır), dağılım sabittir, aynı dağılımdan örnekler alınır.
Training and Test Set :
 
Var olan veri seti; %80 eğitim, %20 test verisi olarak ikeye ayrılabilir. Dikkat edilmesi gerekenler;
•	İstatistiksel olarak anlamlı sonuçlar verecek kadar büyük olmalı.
•	Bir bütün olarak veri kümesini temsil eder (başka veriler kullanılmamalıdır)
Dikkat : Yüksek doğruluk için test verilerinin eğitim setine sızdığını gösterebilir. 
Validation Set :
Validation set, doğrulama için kullanılan bir kümedir. 
 
Şeklinde var olan veri seti üçe ayrılabilir. Amacı, Overfitting’i önlemek için kullanılır. Bir örnek kümesi üzerinde eğitim almanıza ve ardından modeli farklı örneklerle karşı test etmenize olanak tanır.  
 
Dikkat edilmesi gerekenler; eğitim seti sonuçlarını değerlendirmek için doğrulama seti (validation set) kullanılır. Ardından, model doğrulama setini “geçtikten sonra” test seti kullanılır. (Önce train, ardından validation set ile değerlendir. En son test seti ile değerlendir.)
Validation set ile en iyi model seçilebilir sonrasında bu model test set ile iki kez kontrol edilir.

