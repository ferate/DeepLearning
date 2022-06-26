# DeepLearning
DinazoruBulma
 Sistemi eğitmek için kullanılan dataseti bu linkten indirebilirsiniz (Ham Veri,Etiketlenmiş Veri ve Sistemin Hiç Görmediği Test Verileri) :
 https://drive.google.com/drive/folders/1xnZz4z2ktO9eTBDa64D7pqzyPw0MZoCg?usp=sharing
 
 Sadece Etiketlenmiş Verileri İndirmek İçin : https://drive.google.com/drive/folders/1ZokytKX_VjxivF-WkpZ0nTl_Ro5YWtJJ?usp=sharing                    
 
 Sadece Ham Resimleri İndirmek İçin : https://drive.google.com/drive/folders/1ENcFmIhz_6eBeqx0ZeH_jLOQiZaRbLpO?usp=sharing
 
 Sadece Sistemin Hiç Görmediği Test Verilerini İndirmek İçin :https://drive.google.com/drive/folders/1ZvTU0xNa2oEwP5zBdevfkhH8cpzzGh6U?usp=sharing


Colab Kodu :

https://colab.research.google.com/gist/ferate/ad22a0b9e2f3dc180d4caa5ca7218c63/dinazorubul.ipynb







01. Dataseti Oluşturulması


Bu çalışmada bölgesel tabanlı yöntemler kullanılarak nesne tespiti yapabilmek için YOLO V5 kullanılmıştır.

	YOLO V5 kullanılarak tespit edilmek istenen nesne oyuncak bir dinazordur. Veri seti oluşturmak için oyuncak dinazorun değişik açılardan, uzaktan ve yakından resimleri çekilmiştir.

 	 	 
 	 	 

	Daha sonra çekilen resimleri etiketlemek için ücretsiz olarak kullanılabilen https://roboflow.com/ sitesi üzerinden etiketleme işlemi yapılmıştır.
	
	Oluşturulan Derin Öğrenme çalışma alanı içerisine “Dinazor Dataset” adında bir veri seti oluşturulmuştur. Oluşturulan bu veri setine telefon aracılığıyla çekilen 42 adet ham resim Upload edilmiştir. Dataset alanına yüklenen bütün resimler tek tek seçilerek işaretlenmiş ve “Dinazor” olarak etiketlenmiştir.

 
Etiketlenen resimlere Preprocessing (Yeniden boyutlandırma vb), Augmentation (Resmin bir kısmına odaklanma, ters ya da yan çevirme vb işlemler) gibi işlemler yapılarak verilerin artırılması işlemi yapılmış ve toplamda elimizde 113 adet etiketli veri olmuştur.
Etiketlenen verilere Export işlemi yapılarak veri setinin dışarı alınması sağlanmıştır.

 


Projemizde kullanabileceğimiz veri setimiz hazır. Veri setimize ulaşmak için aşağıdaki linklerden birini kullanabilirsiniz :

Sadece Etiketlenmiş Verileri İndirmek İçin :  https://drive.google.com/drive/folders/1ZokytKX_VjxivF-WkpZ0nTl_Ro5YWtJJ?usp=sharing
Sadece Ham Resimleri İndirmek İçin :  https://drive.google.com/drive/folders/1ENcFmIhz_6eBeqx0ZeH_jLOQiZaRbLpO?usp=sharing
Sadece Sistemin Hiç Görmediği Test Verilerini İndirmek İçin : https://drive.google.com/drive/folders/1ZvTU0xNa2oEwP5zBdevfkhH8cpzzGh6U?usp=sharing

 Tamamı İçin (Ham Veri, Etiketlenmiş Veri ve Sistemin Hiç Görmediği Test Verileri) :
 https://drive.google.com/drive/folders/1xnZz4z2ktO9eTBDa64D7pqzyPw0MZoCg?usp=sharing

02.Google Colaboratory Kulanılarak Proje Oluşturulması – Sistemin Eğitilmesi – Test Edilmesi

	Sistemin oluşturulması, eğitilmesi ve test edilmesi için Google Colaboratory uygulaması kullanılmıştır. Uygulamanın kodlarına erişmek için Github ve Colab hesabını ziyaret edebilirsiniz:
https://github.com/ferate/DeepLearning
https://colab.research.google.com/gist/ferate/ad22a0b9e2f3dc180d4caa5ca7218c63/dinazorubul.ipynb


	

Öncelikle YOLO V5 kütüphanesi kullanacağımız için projemize dahil ediyoruz :
 


	Veri setimizi roboflow üzerinden ekleyeceğimiz için gerekli kütüphaneleri ekliyoruz :

           

	Roboflowda oluşturduğumuz veri setini indiriyoruz sisteme dahil ediyoruz :

 

	YOLO V5 Kütüphanesi kullanarak sistemimizi eğitiyoruz :

 

	Bu işlem bilgisayarımızın donanımına ve veri setimizin büyüklüğüne göre biraz zaman alabilir. 

	Sistemin tespit ettiği en iyi modele göre eğitim için kullanmadığımız verilerimizi test edebiliriz :

 

	Sistemin hiç görmediği resimler üzerinden test işlemi yapıldığında tahminleri şu şekilde görebiliriz :

 	 
 	 
 	 



03.Model Değerlendirilmesi

Sisteme dahil edilen 113 adetlik resim ile YOLO V5 kullanılarak eğitilen modelin nesne tespiti konusunda oldukça başarılı olduğu , nesneyi tespit ettiği anlaşıldı. Veriler artırılarak model daha güçlü hale getirilebilir.
