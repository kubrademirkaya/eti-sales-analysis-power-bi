# eti-sales-analysis-power-bi
# Eti Satış Performansı Analiz Raporu - Power BI Projesi

## Proje Genel Bakış

Bu proje, Eti Gıda A.Ş.'nin satış performansını derinlemesine analiz etmek, müşteri davranışlarını anlamak ve ürün kategori trendlerini belirlemek amacıyla Power BI kullanılarak geliştirilmiş interaktif bir iş zekası raporudur. Stratejik kararların verilmesine destek olmak üzere güncel verilerle hazırlanmıştır.

## Temel Özellikler ve Dashboard'lar

Rapor, farklı perspektiflerden satış verilerini sunan üç ana interaktif dashboard sayfası içermektedir:

1.  **Giriş Sayfası:**
    * Raporun ana sayfası olup, genel KPI özetlerini ve diğer analiz sayfalarına hızlı geçiş butonlarını içerir.

2.  **Özet Dashboard:**
    * Toplam Satış Tutarı, Toplam Sipariş Sayısı gibi anahtar performans göstergeleri (KPI'lar) ile genel satış performansı özetlenir.
    * **Günlere Göre Toplam Satış Tutarı**
    * **Bölgelere Göre Toplam Satış Adedi**
    * **Saatlik Toplam Satış Tutarı** (alan grafiği ile)

3.  **Müşteri Analiz Dashboard:**
    * Tekil Müşteri Sayısı, Kadın/Erkek Müşteri Sayısı gibi müşteri odaklı KPI'lar sunulur.
    * **Yaş Grubuna Göre Satış Tutarı**
    * **Bölgelere Göre Müşteri Sayısı**
    * **Cinsiyete Göre Toplam Satış Tutarı**
    * **İstanbul'daki Top 10 Müşteri** (tablo) analizleri içerir.

4.  **Kategori Analiz Dashboard:**
    * Kategori Ortalama Satış, En Çok Satan Kategori gibi kategori odaklı KPI'lar mevcuttur.
    * Ürün kategorilerinin hiyerarşik performanslarını gösteren interaktif bir **Ayrıştırma Ağacı Grafiği** kullanılmıştır.
    * *Not:* Bu görselde, belirli bir proje gereksinimi doğrultusunda **'İstanbul' şehri ve 'Yaşlı' yaş grubu verileri** filtrelenerek gösterilmiştir.

## Tasarım ve Marka Konsepti

Raporun tasarımı, Eti markasının güçlü görsel kimliğini yansıtırken, aynı zamanda veri analizi için optimal okunabilirlik ve kullanıcı deneyimi sağlamak üzere özenle oluşturulmuştur:

* **Renk Paleti:** Eti'nin ana renkleri olan canlı sarı, kırmızı ve siyah, beyaz ile dengeli bir şekilde kullanılmıştır.
    * Analiz sayfalarında sol panel canlı Eti sarısı, ana grafik alanı ise çok açık, pastel sarı bir arka plana sahiptir.
    * Canlı sarı panel üzerindeki filtre kutucukları ve KPI kartları düz beyaz olup, yüksek kontrast ve net okunabilirlik sunar.
* **Navigasyon:** Tutarlı sayfa başlıkları ve sol paneldeki sayfa geçiş butonları ile kullanıcı dostu bir navigasyon sağlanmıştır.

##  Kullanılan Teknolojiler

* **Microsoft Power BI Desktop:** Veri modelleme, ETL (Extract, Transform, Load) süreçleri, DAX (Data Analysis Expressions) ölçüleri oluşturma ve etkileşimli görselleştirmeler tasarlama için kullanılmıştır.
* **Python (Pandas, SciPy):** Veri setinin detaylı istatistiksel analizleri (ortalama, medyan, standart sapma, vb.) için kullanılmıştır.
* **Microsoft Excel:** Büyük veri setleri için istatistiksel özetlerin doğrulanması ve belirli hesaplamaların yapılması amacıyla destekleyici araç olarak kullanılmıştır.

##  Veri İstatistikleri Hesaplaması

Projede kullanılan ana sayısal kolonların (örneğin `TOTALPRICE`, `AMOUNT`, `unitprice`, `linetotal`) temel istatistiksel özellikleri (ortalama, medyan, standart sapma, minimum, maksimum, çeyreklikler) Python'da Pandas kütüphanesi ve Excel'deki ilgili fonksiyonlar kullanılarak detaylı bir şekilde analiz edilmiştir. Bu istatistikler, veri setinin yapısını, potansiyel aykırı değerleri ve dağılımın şeklini anlamada kritik rol oynamıştır.

## Projeyi Açma ve Kullanma

1.  Bu GitHub deposunu klonlayın veya zip olarak indirin.
2.  'EtiSatisAnalizDashboard.zip' içindeki `EtiSatisAnalizDashboard.pbix` dosyasını Microsoft Power BI Desktop ile açın.
3.  Rapor sayfaları arasında gezinmek için sol paneldeki navigasyon butonlarını ve filtreleri kullanın.
4.  Görselleştirmelerle etkileşime geçerek verileri keşfedin.

## Veri Modeli

Projede kullanılan veri modeli, boyut tabloları (`kullanıcılar`, `Urunler`, `Adres`, `bölgeler`) ve olgu tabloları (`siparis`, `siparisdetay`) içeren iyi yapılandırılmış bir yıldız şemasına sahiptir. Bu modelleme, raporun performansını ve analiz yeteneğini artırır.

* **Olgu Tablosu (Fact Table):** İş süreçlerindeki olayları (örn. satışlar, siparişler) temsil eden, genellikle sayısal ve ölçülebilir veriler (örn. toplam fiyat, miktar) içeren tablolardır. Boyut tablolarıyla ilişkiler kurarak analizlerin temelini oluştururlar. Projemizde `siparis` ve `siparisdetay` tabloları olgu tablolarıdır.
* **Boyut Tablosu (Dimension Table):** İşlemlerin (olgu tablosu) bağlamını veya niteliklerini tanımlayan tablolardır. Bu tablolar, "kim?", "ne?", "nerede?", "ne zaman?" gibi sorulara yanıt veren nitel bilgiler (örn. müşteri adı, ürün kategorisi, tarih) içerir. Projemizde `kullanıcılar`, `Urunler`, `Adres`, `bölgeler` tabloları boyut tablolarıdır.

---
