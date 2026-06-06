# 🤖 IBM Granite ile Uzun Doküman Özetleme Projesi

Bu proje, **IBM'in Granite LLM (Büyük Dil Modeli)** mimarisini kullanarak, normal şartlarda yapay zeka modellerinin hafıza sınırını (Context Window) aşan çok uzun edebi eserleri veya dokümanları akıllıca parçalara bölüp özetleyen bir yapay zeka uygulamasıdır.

Bu çalışma, **IBM** tarafından sunulan yapay zeka eğitiminin bir parçası olarak **Google Colab** ortamında geliştirilmiştir.

---

## 🚀 Projenin Amacı ve Çözdüğü Problem
Büyük dil modellerine (LLM) devasa bir kitabı tek seferde girdi olarak vermek hafıza yetersizliğinden (**Out of Memory**) dolayı imkansızdır. 

Bu projede, Henry David Thoreau'nun klasik eseri **Walden** (18 bölümden oluşan dev bir metin) kullanılmıştır. Geliştirilen mimari sayesinde:
1. Uzun metin otomatik olarak yönetilebilir parçalara (**Chunking**) bölünmüştür.
2. Her parça bulut üzerinde çalışan **IBM Granite** modeline gönderilmiştir.
3. Model, on binlerce token'lık veriyi pürüzsüzce işleyerek her bölüm için rafine özetler üretmiştir.

---

## 🛠️ Kullanılan Teknolojiler ve Altyapı
* **Geliştirme Ortamı:** Google Colab (Python 3)
* **Yapay Zeka Modeli:** IBM Granite (LLM)
* **Bulut Sağlayıcı / API:** Replicate (Modelin serverless olarak çalıştırılması için)
* **Veri Seti:** *Walden* (Edebi Eser - 18 Bölüm)

---

## 📈 Proje Çıktıları ve Performans
Sistem hız sınırlarına (**Rate Limit - 429**) takılmamak adına kod seviyesinde zaman gecikmeleri (`time.sleep`) eklenerek optimize edilmiştir.

**Örnek Bir Bölüm Performansı:**
* **Giriş Boyutu (Input):** ~36,076 Token (Yaklaşık 27.000 kelime)
* **Çıkış Boyutu (Output):** ~212 Token (Net, rafine özet)
* **Sonuç:** Yapay zeka, metnin ana fikrini ve edebi derinliğini kaybetmeden devasa bir veriyi saniyeler içinde özetlemeyi başarmıştır.

---

## 💻 Nasıl Çalıştırılır?
1. Bu depodaki `.ipynb` dosyasını Google Colab üzerinde açın.
2. Bir **Replicate** hesabı oluşturarak API Token'ınızı alın.
3. Colab'ın "Secrets" (Anahtar) kısmına token'ınızı ekleyin.
4. Hücreleri sırayla çalıştırın.
