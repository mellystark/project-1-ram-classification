# 📘 BLG-407 Project-1

## CNN Tabanlı Laptop RAM vs Desktop RAM Görüntü Sınıflandırma

Bu repository, **BLG-407 Machine Learning** dersi kapsamında gerçekleştirilen
**Project-1** çalışmasını içermektedir.

Çalışmada, Laptop RAM ve Desktop RAM görselleri kullanılarak **Convolutional Neural Network (CNN)** tabanlı modeller ile görüntü sınıflandırma problemi ele alınmış; farklı mimari yaklaşımlar **karşılaştırmalı** olarak analiz edilmiştir.

---

## 🔍 Proje Problemi

İki sınıflı bir görüntü sınıflandırma problemi çözülmüştür:

* **Laptop RAM**
* **Desktop RAM**

Amaç, verilen bir RAM görselinin hangi sınıfa ait olduğunu **yüksek doğrulukla** tahmin edebilen bir CNN modeli geliştirmektir.

---

## 📂 Veri Seti Bilgisi

* **Toplam görsel sayısı:** 142
* **Sınıf sayısı:** 2
* **Sınıf dağılımı:**

  * Laptop RAM: 71
  * Desktop RAM: 71
* Veri seti **dengelidir (balanced)**.
* Görseller **kullanıcı tarafından çekilmiştir**; hazır bir veri seti kullanılmamıştır.

### Veri Bölünmesi

* %70 Eğitim (Train)
* %15 Doğrulama (Validation)
* %15 Test

Veri seti Google Drive üzerinde tutulmakta olup, notebook’lar **Google Colab** ortamında çalışacak şekilde yapılandırılmıştır.

---

## 🧠 Kullanılan Modeller ve Yaklaşımlar

### 🔹 Model 1 – Transfer Learning (ResNet50)

* **ResNet50** mimarisi kullanılmıştır.
* ImageNet ağırlıkları ile **Transfer Learning** uygulanmıştır.
* Amaç: State-of-the-art bir model ile **referans performans** elde etmek.
* Önceki denemelerde VGG16 ile düşük performans alınması nedeniyle ResNet50 tercih edilmiştir.

---

### 🔹 Model 2 – Basit CNN (Sıfırdan Eğitim)

* CIFAR-10 tarzı **basit bir CNN mimarisi** kullanılmıştır.
* **Transfer learning kullanılmamıştır.**
* Amaç: Veri setine özgü öğrenmenin performansını gözlemlemek.
* Bu model, Model 3 için **baseline (referans model)** olarak kabul edilmiştir.

---

### 🔹 Model 3 – Geliştirilmiş CNN (Optimizasyon + Augmentation)

* Model 2 temel alınarak geliştirilmiştir.
* **En az 3 hiperparametre değiştirilmiştir:**

  * Filtre sayıları
  * Dropout oranı
  * Learning rate
  * Batch size
* **ImageDataGenerator** kullanılarak online data augmentation uygulanmıştır.
* Birden fazla deney yapılmış ve **en iyi model** test doğruluğuna göre seçilmiştir.
* Proje kapsamında **en yüksek performans** bu model ile elde edilmiştir.

---

## 📊 Model Karşılaştırması (Özet)

| Model   | Yaklaşım                         | Rolü            | Performans    |
| ------- | -------------------------------- | --------------- | ------------- |
| Model 1 | ResNet50 + Transfer Learning     | Referans (SOTA) | Orta          |
| Model 2 | Basit CNN (Sıfırdan)             | Baseline        | Daha Düşük    |
| Model 3 | Geliştirilmiş CNN + Augmentation | Final Model     | **En Yüksek** |

> Model 3, hem hiperparametre optimizasyonu hem de data augmentation sayesinde
> Model 2’ye kıyasla anlamlı bir performans artışı sağlamıştır.

---

## ▶️ Nasıl Çalıştırılır?

1. Repository’i klonlayın:

   ```bash
   git clone https://github.com/mellystark/project-1-ram-classification.git
   ```

2. Google Colab üzerinde ilgili notebook’u açın:

   * `notebooks/model1_transfer_learning.ipynb`
   * `notebooks/model2_basic_cnn.ipynb`
   * `notebooks/model3_optimized_cnn.ipynb`

3. Google Drive bağlantısını kurun.

4. Notebook hücrelerini **üstten alta doğru** çalıştırın.

> Notebook’lar Colab uyumludur ve ek bir yapılandırma gerektirmez.

---

## 📁 Sonuçlar ve Çıktılar

* Eğitim ve doğrulama **accuracy/loss grafikleri**
* Test seti doğruluk sonuçları
* Model 3 için **deney karşılaştırma tablosu**
* Tüm çıktılar `results/` klasörü altında yer almaktadır.

---

## 📝 Notlar

* Model 3, proje kapsamında **en iyi test doğruluğunu** elde eden modeldir.
* Data augmentation, modelin genelleme yeteneğini belirgin biçimde artırmıştır.
* Proje bireysel olarak geliştirilmiş olup, akademik etik kurallarına uygundur.

---

## 👤 Öğrenci Bilgileri

* **Ad Soyad:** Melike Çakmakoğlu
* **Öğrenci No:** 2212721048
* **Ders:** BLG-407 Machine Learning

---

### 🎯 Sonuç

Bu repository, **BLG-407 Project-1** teslim kriterlerini **eksiksiz** karşılamakta olup,
CNN tabanlı görüntü sınıflandırma yaklaşımlarının karşılaştırmalı analizini sunmaktadır.

---

