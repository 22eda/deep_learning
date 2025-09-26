Yüz İfadesi Tanıma Projesi -CNN DEEP LEARNİNG

KAGGLE PROJE LİNK: https://www.kaggle.com/code/edanurdemirel/cnn-emotion-detection?scriptVersionId=264191317
KAGGLE VERİ SETİ: https://www.kaggle.com/datasets/deadskull7/fer2013

Giriş
Bu proje, FER2013 veri setini kullanarak yüz ifadelerini tanımak için Evrişimsel Sinir Ağları (CNN) modelleri geliştirmeyi amaçlamaktadır. Proje kapsamında, sıfırdan oluşturulan bir temel CNN modeli ile önceden eğitilmiş bir VGG16 modeline dayanan transfer öğrenme modeli karşılaştırılmıştır.

Kullanılan Metodoloji
Projede iki ana yaklaşım izlenmiştir:

Temel CNN Modeli: Küçük, gri tonlamalı görüntüler için optimize edilmiş, tamamen sıfırdan bir Evrişimsel Sinir Ağı mimarisi oluşturulmuştur. Bu model, veri setinin özelliklerini en iyi şekilde öğrenmek üzere tasarlanmıştır.

Transfer Öğrenme Modeli: ImageNet veri setinde eğitilmiş olan VGG16 modeli, bir özellik çıkarıcı olarak kullanılmıştır. Bu modelin üzerine, duygu sınıflandırması için yeni bir çıkış katmanı eklenerek ince ayar yapılmıştır.

Veri Ön İşleme ve Çoğaltma
Modellerin daha iyi genelleme yapabilmesi için aşağıdaki adımlar uygulanmıştır:

Görüntüler normalize edilerek 0-1 aralığına getirilmiştir.

ImageDataGenerator kullanılarak döndürme, kaydırma ve yakınlaştırma gibi tekniklerle veri çoğaltma yapılmıştır.

Proje Sonuçları ve Analiz
Modellerin test verisi üzerindeki performansı şu şekildedir:

Temel CNN Modeli Doğruluğu: %84.89

Transfer Öğrenme Modeli Doğruluğu: %60.41

Analiz: Bu sonuçlar, kendi oluşturduğumuz temel CNN modelinin, transfer öğrenme modeline kıyasla çok daha başarılı olduğunu göstermektedir. Bunun ana nedeni, FER2013 veri setinin gri tonlamalı ve düşük çözünürlüklü olmasıdır. VGG16'nın ImageNet'ten öğrendiği özellikler, yüz ifadesi gibi spesifik ve küçük detayları tanımak için yeterli olmamıştır. Temel CNN modelimiz ise doğrudan bu göreve özel olarak eğitildiği için daha yüksek doğruluk oranına ulaşmıştır.

Optimizasyon Karşılaştırması
Farklı optimizasyon algoritmaları da test edilmiş ve en iyi sonucu veren Adam optimizer olmuştur.

Sonuç
Bu proje, bir göreve özgü olarak tasarlanmış basit bir modelin, her zaman en iyi çözüm olmayabilecek daha karmaşık bir transfer öğrenme modelinden daha iyi performans gösterebileceğini kanıtlamıştır.

Gereksinimler
Projenin çalışması için gerekli temel kütüphaneler:

tensorflow
keras
numpy
pandas
matplotlib
seaborn
scikit-learn
