1) Naive Bayes Sınıflandırıcısı Sonuçlarının Açıklaması
Karışıklık Matrisi:
[[119  32]
 [ 27  53]]
Karışıklık matrisi, sınıflandırma sonuçlarının bir özetini sunar:

•	Doğru Negatifler (TN): 119 - Doğru tahmin edilen negatiflerin (sınıf 0) sayısı.
•	Yanlış Pozitifler (FP): 32 - Yanlış tahmin edilen pozitiflerin (sınıf 1 olarak tahmin edilip aslında sınıf 0 olanların) sayısı.
•	Yanlış Negatifler (FN): 27 - Yanlış tahmin edilen negatiflerin (sınıf 0 olarak tahmin edilip aslında sınıf 1 olanların) sayısı.
•	Doğru Pozitifler (TP): 53 - Doğru tahmin edilen pozitiflerin (sınıf 1) sayısı.
Sınıflandırma Raporu:
              precision    recall  f1-score   support
         0.0       0.82      0.79      0.80       151
         1.0       0.62      0.66      0.64        80
    accuracy                           0.74       231
   macro avg       0.72      0.73      0.72       231
weighted avg       0.75      0.74      0.75       231

•	Precision (Hassasiyet): Doğru tahmin edilen pozitif gözlemlerin toplam tahmin edilen pozitif gözlemlere oranı. Sınıf 0 için 0.82 hassasiyet, tahmin edilen sınıf 0 gözlemlerin %82'sinin doğru olduğunu gösterir. Sınıf 1 için 0.62 hassasiyet, tahmin edilen sınıf 1 gözlemlerin %62'sinin doğru olduğunu gösterir.
•	Recall (Duyarlılık): Doğru tahmin edilen pozitif gözlemlerin, gerçek sınıftaki tüm gözlemlere oranı. Sınıf 0 için 0.79 duyarlılık, gerçek sınıf 0 gözlemlerin %79'unun doğru şekilde tanımlandığını gösterir. Sınıf 1 için 0.66 duyarlılık, gerçek sınıf 1 gözlemlerin %66'sının doğru şekilde tanımlandığını gösterir.
•	F1-Skoru: Hassasiyet ve duyarlılığın ağırlıklı ortalaması olup, hem yanlış pozitifleri hem de yanlış negatifleri dikkate alır. Sınıf 0 için F1-skoru 0.80, sınıf 1 için 0.64'tür.
•	Destek (Support): Test setindeki her sınıfın gerçek ortaya çıkma sayısı (sınıf 0 için 151, sınıf 1 için 80).

Genel Metrikler:
•	Doğruluk (Accuracy): Doğru tahmin edilen gözlemlerin toplam gözlemlere oranı, bu durumda %74'tür.
•	Makro Ortalama (Macro Avg): Hassasiyet, duyarlılık ve F1-skorunun ağırlıksız ortalaması.
•	Ağırlıklı Ortalama (Weighted Avg): Her sınıfın destek miktarını dikkate alarak hesaplanan hassasiyet, duyarlılık ve F1-skorunun ağırlıklı ortalaması.

Ortalama Kare Hata (Mean Squared Error):
0.2554112554112554
Ortalama Kare Hata (MSE), tahmin edilen ve gerçek değerler arasındaki kare farklarının ortalamasıdır. 0.255 MSE, tahminlerde orta düzeyde hata olduğunu gösterir.

ROC AUC Skoru:
0.7904801324503311
ROC AUC skoru, Alıcı İşletim Karakteristiği (ROC) eğrisinin altındaki alanı temsil eder. Bu skor, sınıflandırıcının sınıfları ayırt etme yeteneğini ölçer. 0.79'luk bir skor, sınıflandırıcının çoğu zaman pozitif ve negatif sınıfları doğru bir şekilde ayırt ettiğini gösterir.

Özet
Naive Bayes sınıflandırıcısı şunları gösterir:
•	%74'lük makul bir genel doğruluk.
•	Sınıf 0 için sınıf 1'e kıyasla daha iyi hassasiyet ve duyarlılık.
•	Tahmin hatalarını gösteren orta düzeyde bir ortalama kare hata.
•	İyi bir ayrım yeteneği gösteren iyi bir ROC AUC skoru.
Sınıflandırıcı genel olarak iyi performans gösterir, ancak özellikle sınıf 1 tahminleri için iyileştirmeler yapılabilir.

2) K-En Yakın Komşu (KNN) Sınıflandırıcısı Sonuçlarının Açıklaması
En İyi KNN Parametreleri:
{'n_neighbors': 23, 'weights': 'distance'}
GridSearchCV ile yapılan hiperparametre ayarlaması, en iyi KNN modelinin 23 komşu (`n_neighbors=23`) kullandığını ve komşuları mesafelerine göre ağırlıklandırdığını (`weights='distance'`) belirledi. Bu, daha yakın komşuların sınıflandırma kararında daha fazla etkiye sahip olduğu anlamına gelir.
Karışıklık Matrisi:
[[130  21]
 [ 42  38]]
Karışıklık matrisi, sınıflandırma sonuçlarının bir özetini sunar:
•	Doğru Negatifler (TN): 130 - Doğru tahmin edilen negatifler (sınıf 0).
•	Yanlış Pozitifler (FP): 21 - Yanlış tahmin edilen pozitifler (sınıf 1 olarak tahmin edilip aslında sınıf 0 olanlar).
•	Yanlış Negatifler (FN): 42 - Yanlış tahmin edilen negatifler (sınıf 0 olarak tahmin edilip aslında sınıf 1 olanlar).
•	Doğru Pozitifler (TP): 38 - Doğru tahmin edilen pozitifler (sınıf 1).

Sınıflandırma Raporu:
              precision    recall  f1-score   support

         0.0       0.76      0.86      0.80       151
         1.0       0.64      0.47      0.55        80

    accuracy                           0.73       231
   macro avg       0.70      0.67      0.68       231
weighted avg       0.72      0.73      0.72       231

•	Precision (Hassasiyet): Sınıf 0: 0.76 - Tahmin edilen sınıf 0 örneklerin %76'sı doğru. Sınıf 1: 0.64 - Tahmin edilen sınıf 1 örneklerin %64'ü doğru.
•	Recall (Duyarlılık): Sınıf 0: 0.86 - Gerçek sınıf 0 örneklerin %86'sı doğru tanımlandı. Sınıf 1: 0.47 - Gerçek sınıf 1 örneklerin %47'si doğru tanımlandı.
•	F1-Skoru: Sınıf 0: 0.80 - Sınıf 0 için hassasiyet ve duyarlılığın harmonik ortalaması. Sınıf 1: 0.55 - Sınıf 1 için hassasiyet ve duyarlılığın harmonik ortalaması.
•	Destek (Support): Her sınıftaki örnek sayısı (sınıf 0 için 151 ve sınıf 1 için 80).

Genel Metrikler:
•	Doğruluk (Accuracy): %73 - Doğru tahmin edilen örneklerin toplam örnek sayısına oranı.
•	Makro Ortalama (Macro Avg): 0.70 (hassasiyet), 0.67 (duyarlılık), 0.68 (F1-skora) - Hassasiyet, duyarlılık ve F1-skorunun ağırlıksız ortalaması.
•	Ağırlıklı Ortalama (Weighted Avg): 0.72 (hassasiyet), 0.73 (duyarlılık), 0.72 (F1-skora) - Her sınıfın destek miktarını dikkate alarak hesaplanan hassasiyet, duyarlılık ve F1-skora'nın ağırlıklı ortalaması.

Ortalama Kare Hata (Mean Squared Error):
0.2727272727272727
Ortalama Kare Hata (MSE), tahmin edilen ve gerçek değerler arasındaki kare farklarının ortalamasıdır. 0.273 MSE, tahminlerde orta düzeyde hata olduğunu gösterir.

ROC AUC Skoru:
0.7860927152317881
ROC AUC skoru, Alıcı İşletim Karakteristiği (ROC) eğrisinin altındaki alanı temsil eder. Bu skor, sınıflandırıcının sınıfları ayırt etme yeteneğini ölçer. 0.786'lık bir skor, modelin pozitif ve negatif sınıfları ayırt etmede iyi bir yeteneğe sahip olduğunu gösterir.

Özet
En iyi parametrelerle KNN sınıflandırıcısı:
•	Naive Bayes sınıflandırıcısına kıyasla benzer bir doğruluk (%73) elde eder.
•	Sınıf 0 için iyi hassasiyet ve duyarlılık gösterir, ancak sınıf 1 için daha düşük duyarlılık gösterir, bu da birçok sınıf 1 örneğinin sınıf 0 olarak yanlış sınıflandırıldığını gösterir.
•	Orta düzeyde bir ortalama kare hataya sahiptir.
•	İyi bir ayrım gücü gösteren iyi bir ROC AUC skoruna sahiptir.

KNN sınıflandırıcısı genel olarak makul performans gösterir ancak özellikle sınıf 1 örneklerini daha doğru tanımlamada iyileştirilebilir. Bu, modelin diyabet olmayan vakaları (sınıf 0) tanımlamada iyi olduğunu ancak diyabet vakalarını (sınıf 1) doğru tanımlamada daha çok zorlandığını göstermektedir.

3) Çok Katmanlı Algılayıcı (MLP) Sınıflandırıcı Sonuçlarının Açıklaması
En İyi MLP Parametreleri:
{'activation': 'relu', 'alpha': 0.05, 'hidden_layer_sizes': (50,), 'learning_rate': 'constant', 'solver': 'adam'}
GridSearchCV ile yapılan hiperparametre ayarlaması, en iyi MLP model parametrelerini belirledi:
•	activation: 'relu' (Düzeltimli Doğrusal Birim) - modele doğrusal olmayanlık kazandıran yaygın olarak kullanılan bir aktivasyon fonksiyonu.
•	alpha: 0.05 - aşırı öğrenmeyi önlemek için düzenleme terimi.
•	hidden_layer_sizes: (50) - 50 nöronlu tek gizli katman.
•	learning_rate: 'constant' - öğrenme oranı eğitim sırasında sabit kalır.
•	solver: 'adam' - AdaGrad ve RMSProp'un avantajlarını birleştiren bir optimizasyon algoritması.

Karışıklık Matrisi:
[[122  29]
 [ 31  49]]
Karışıklık matrisi, sınıflandırma sonuçlarının bir özetini sunar:
•	Doğru Negatifler (TN): 122 - Doğru tahmin edilen negatifler (sınıf 0).
•	Yanlış Pozitifler (FP): 29 - Yanlış tahmin edilen pozitifler (sınıf 1 olarak tahmin edilip aslında sınıf 0 olanlar).
•	Yanlış Negatifler (FN): 31 - Yanlış tahmin edilen negatifler (sınıf 0 olarak tahmin edilip aslında sınıf 1 olanlar).
•	Doğru Pozitifler (TP): 49 - Doğru tahmin edilen pozitifler (sınıf 1).

Sınıflandırma Raporu:
              precision    recall  f1-score   support

         0.0       0.80      0.81      0.80       151
         1.0       0.63      0.61      0.62        80

    accuracy                           0.74       231
   macro avg       0.71      0.71      0.71       231
weighted avg       0.74      0.74      0.74       231

•	Precision (Hassasiyet): Sınıf 0: 0.80 - Tahmin edilen sınıf 0 örneklerinin %80'i doğru. Sınıf 1: 0.63 - Tahmin edilen sınıf 1 örneklerinin %63'ü doğru.
•	Recall (Duyarlılık): Sınıf 0: 0.81 - Gerçek sınıf 0 örneklerinin %81'i doğru tanımlandı. Sınıf 1: 0.61 - Gerçek sınıf 1 örneklerinin %61'i doğru tanımlandı.
•	F1-Skoru: Sınıf 0: 0.80 - Sınıf 0 için hassasiyet ve duyarlılığın harmonik ortalaması. Sınıf 1: 0.62 - Sınıf 1 için hassasiyet ve duyarlılığın harmonik ortalaması.
•	 Destek (Support): Her sınıftaki örnek sayısı (sınıf 0 için 151 ve sınıf 1 için 80).

Genel Metrikler:
•	Doğruluk (Accuracy): %74 - Doğru tahmin edilen örneklerin toplam örnek sayısına oranı.
•	Makro Ortalama (Macro Avg): 0.71 (hassasiyet), 0.71 (duyarlılık), 0.71 (F1-skora) - Hassasiyet, duyarlılık ve F1-skora'nın ağırlıksız ortalaması.
•	Ağırlıklı Ortalama (Weighted Avg): 0.74 (hassasiyet), 0.74 (duyarlılık), 0.74 (F1-skora) - Her sınıfın destek miktarını dikkate alarak hesaplanan hassasiyet, duyarlılık ve F1-skora'nın ağırlıklı ortalaması.
Ortalama Kare Hata (Mean Squared Error):
0.2597402597402597
Ortalama Kare Hata (MSE), tahmin edilen ve gerçek değerler arasındaki kare farklarının ortalamasıdır. 0.26 MSE, tahminlerde orta düzeyde hata olduğunu gösterir.
ROC AUC Skoru:
0.804635761589404
ROC AUC skoru, Alıcı İşletim Karakteristiği (ROC) eğrisinin altındaki alanı temsil eder. Bu skor, sınıflandırıcının sınıfları ayırt etme yeteneğini ölçer. 0.805'lik bir skor, modelin pozitif ve negatif sınıfları ayırt etmede iyi bir yeteneğe sahip olduğunu gösterir.
Özet
En iyi parametrelerle MLP sınıflandırıcısı:
•	Naive Bayes ve KNN sınıflandırıcılarına benzer bir doğruluk (%74) elde eder.
•	Sınıf 0 için iyi hassasiyet ve duyarlılık gösterir, ancak sınıf 1 için biraz daha düşük.
•	Orta düzeyde bir ortalama kare hataya sahiptir.
•	İyi bir ayrım gücü gösteren iyi bir ROC AUC skoruna sahiptir.

MLP sınıflandırıcısı genel olarak iyi performans gösterir, özellikle sınıfları ayırt etmede. Naive Bayes ve KNN sınıflandırıcılarına kıyasla biraz daha iyi ROC AUC skoru göstererek, verideki karmaşık ilişkileri daha iyi yönetme yeteneğini gösterir.

4) Destek Vektör Makineleri (SVM) Sınıflandırıcı Sonuçlarının Açıklaması
En İyi SVM Parametreleri:
{'C': 100, 'gamma': 1, 'kernel': 'linear'}
GridSearchCV ile yapılan hiperparametre ayarlaması, en iyi SVM model parametrelerini belirledi:
•	C: 100 - Eğitim hatası ile test hatası arasındaki dengeyi kontrol eden düzenleme parametresi. Daha yüksek bir C değeri, modelin eğitim verilerini daha iyi uyarlamaya çalıştığı anlamına gelir.
•	gamma: 1 - 'rbf', 'poly' ve 'sigmoid' için çekirdek katsayısı. 'linear' çekirdek kullandığımız için gamma doğrudan kullanılmaz.
•	kernel: 'linear' - SVM için doğrusal bir çekirdek kullanımını belirtir.

Karışıklık Matrisi:
[[123  28]
 [ 30  50]]
Karışıklık matrisi, sınıflandırma sonuçlarının bir özetini sunar:
•	Doğru Negatifler (TN): 123 - Doğru tahmin edilen negatifler (sınıf 0).
•	Yanlış Pozitifler (FP): 28 - Yanlış tahmin edilen pozitifler (sınıf 1 olarak tahmin edilip aslında sınıf 0 olanlar).
•	Yanlış Negatifler (FN): 30 - Yanlış tahmin edilen negatifler (sınıf 0 olarak tahmin edilip aslında sınıf 1 olanlar).
•	Doğru Pozitifler (TP): 50 - Doğru tahmin edilen pozitifler (sınıf 1).

Sınıflandırma Raporu:
              precision    recall  f1-score   support

         0.0       0.80      0.81      0.81       151
         1.0       0.64      0.62      0.63        80

    accuracy                           0.75       231
   macro avg       0.72      0.72      0.72       231
weighted avg       0.75      0.75      0.75       231

•	Precision (Hassasiyet): Sınıf 0: 0.80 - Tahmin edilen sınıf 0 örneklerinin %80'i doğru. Sınıf 1: 0.64 - Tahmin edilen sınıf 1 örneklerinin %64'ü doğru.
•	Recall (Duyarlılık): Sınıf 0: 0.81 - Gerçek sınıf 0 örneklerinin %81'i doğru tanımlandı. Sınıf 1: 0.62 - Gerçek sınıf 1 örneklerinin %62'si doğru tanımlandı.
•	F1-Skoru: Sınıf 0: 0.81 - Sınıf 0 için hassasiyet ve duyarlılığın harmonik ortalaması. Sınıf 1: 0.63 - Sınıf 1 için hassasiyet ve duyarlılığın harmonik ortalaması.
•	Destek (Support): Her sınıftaki örnek sayısı (sınıf 0 için 151 ve sınıf 1 için 80).

Genel Metrikler:
•	Doğruluk (Accuracy): %75 - Doğru tahmin edilen örneklerin toplam örnek sayısına oranı.
•	Makro Ortalama (Macro Avg): 0.72 (hassasiyet), 0.72 (duyarlılık), 0.72 (F1-skora) - Hassasiyet, duyarlılık ve F1-skora'nın ağırlıksız ortalaması.
•	Ağırlıklı Ortalama (Weighted Avg): 0.75 (hassasiyet), 0.75 (duyarlılık), 0.75 (F1-skora) - Her sınıfın destek miktarını dikkate alarak hesaplanan hassasiyet, duyarlılık ve F1-skora'nın ağırlıklı ortalaması.

Ortalama Kare Hata (Mean Squared Error):
0.2510822510822511
Ortalama Kare Hata (MSE), tahmin edilen ve gerçek değerler arasındaki kare farklarının ortalamasıdır. 0.251 MSE, tahminlerde orta düzeyde hata olduğunu gösterir.

ROC AUC Skoru:
0.8028145695364238
ROC AUC skoru, Alıcı İşletim Karakteristiği (ROC) eğrisinin altındaki alanı temsil eder. Bu skor, sınıflandırıcının sınıfları ayırt etme yeteneğini ölçer. 0.803'lik bir skor, modelin pozitif ve negatif sınıfları ayırt etmede iyi bir yeteneğe sahip olduğunu gösterir.

Özet
En iyi parametrelerle SVM sınıflandırıcısı:
•	Naive Bayes, KNN ve MLP sınıflandırıcılarından biraz daha yüksek olan %75 doğruluğa ulaşır.
•	Sınıf 0 için iyi hassasiyet ve duyarlılık gösterir, ancak diğer modeller gibi sınıf 1 için daha düşük.
•	Orta düzeyde bir ortalama kare hataya sahiptir.
•	İyi bir ayrım gücü gösteren iyi bir ROC AUC skoruna sahiptir.

SVM sınıflandırıcısı genel olarak iyi performans gösterir, özellikle sınıfları ayırt etmede. Doğruluğu ve ROC AUC skoru, Naive Bayes ve KNN sınıflandırıcılarına göre biraz daha iyidir, bu da veriyi iyi bir şekilde ele aldığını gösterir. Bu, SVM'yi bu sınıflandırma görevi için rekabetçi bir seçenek haline getirir ve çeşitli metrikler boyunca sağlam performans sergilediğini gösterir.
