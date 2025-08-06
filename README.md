# 🛍️ Who Will Buy Again? - Retail ML + Segmentation

Bu proje, bir e-ticaret veri seti üzerinden müşterilerin tekrar alışveriş yapma olasılığını tahmin etmeye odaklanan bir makine öğrenmesi çalışmasıdır.  
Amaç, müşteri davranışlarını analiz ederek pazarlama stratejilerini daha akıllı hale getirmek ve işletme kaynaklarını daha verimli kullanmaktır.

## 🎯 Proje Hedefleri

- RFM analiziyle müşteri segmentasyonu yapmak  
- Müşterilerin tekrar alışveriş yapma ihtimalini sınıflandırma modeli ile tahmin etmek  
- Kampanya hedeflemelerini veri odaklı şekilde optimize etmek  

## 📦 Kullanılan Veri Seti

Veri seti; müşteri kimlikleri, sipariş tarihleri, sipariş miktarları ve ürün bilgilerini içermektedir.  
Veri ön işleme aşamasında:

- Eksik değerler temizlendi  
- Ayıklayıcı özellik mühendisliği adımları uygulandı  
- RFM skorları oluşturuldu  
- Yeni değişkenler eklendi (alışveriş sıklığı, son alışverişten geçen gün sayısı vb.)

## ⚙️ Kullanılan Model

Model: `LightGBM Classifier`

Model, **sınıf 1 (tekrar alışveriş yapacak müşteriler)** için oldukça başarılı sonuçlar vermektedir. Ancak **sınıf 0 (alışveriş yapmayacak müşteriler)** için düşük performans dikkat çekicidir.

## 💡 Yorumlar ve Çıkarımlar

- Model genel olarak yüksek doğrulukla çalışmakta (Accuracy: %93).
- **Sınıf 1 (alışveriş yapacak)** için precision ve recall değerleri oldukça yüksek.
- Ancak **sınıf 0 (alışveriş yapmayacak)** için recall değeri %57 gibi düşük bir seviyede.  
  Bu da modelin çok sayıda müşteriyi yanlışlıkla “alışveriş yapacak” olarak tahmin etmesine neden oluyor (**false positive sayısı: 3554**).
- Bu durum, kampanya maliyetlerinin artmasına yol açabilir.

## 🚧 Eksikler ve Gelecek Planlar

Bu aşamada model sınıf 1’i iyi öğrenmiş olsa da, sınıf 0’ı yeterince iyi ayırt edememektedir.  
Zaman kısıtları nedeniyle bu noktada modellemeyi tamamladım ancak:

- Sınıf dengesizliğini azaltmak için **SMOTE, class weighting** gibi yöntemler
- **Model karmaşıklığını azaltarak** overfitting’i önlemek
- Daha dengeli bir performans için **farklı model denemeleri ve parametre ayarları**  
gibi geliştirme planlarım bulunmakta.

## 📌 Not

Bu proje, hem segmentasyon hem de sınıflandırma açısından e-ticaret veri analitiği problemlerine bütünsel bir yaklaşım sunmayı hedeflemektedir.  
İleride daha da optimize edilmiş, uçtan uca çalışan bir pipeline’a dönüştürülmesi planlanmaktadır.
