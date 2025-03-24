# 🚇 Metro Rota Optimizasyon Sistemi

Bu proje, bir metro ağındaki en kısa ve en az aktarmalı rotaları bulan Python tabanlı bir uygulamadır. 

Kullanıcıların başlangıç ve varış istasyonlarını girerek optimal rotaları görmesini sağlar.

## 🛠 Kullanılan Teknolojiler ve Kütüphaneler

- **Python 3**
- Kütüphaneler:
  - `collections.defaultdict`: Graf yapısını verimli şekilde tutmak için
  - `collections.deque`: BFS'de kuyruk yönetimi için
  - `heapq`: A* algoritmasında öncelik kuyruğu için
  - `typing`: Tip ipuçları (type hints) için

## 🧠 Algoritmaların Çalışma Mantığı

### 1️⃣ BFS (En Az Aktarma)
- **Nasıl Çalışır?**  
  Genişlik öncelikli arama (BFS), başlangıç istasyonundan tüm komşuları tarayarak hedefe ulaşır. Aktarma sayısını minimize eder.

- **Neden Kullandık?**  
  Aktarma sayısı önemli olduğunda (örneğin yolcu konforu) ideal çözümü verir.

### 2️⃣ Dijkstra/A* (En Hızlı Rota)
- **Nasıl Çalışır?**  
  A* algoritması, her adımda tahmini maliyet (heuristic) ile gerçek maliyeti toplayarak en optimize rotayı bulur. Projede heuristic=0 kullanıldığı için Dijkstra gibi davranır.

- **Neden Kullandık?**  
  Seyahat süresini minimize etmek için en etkili yöntemdir.

## 📊 Örnek Kullanım ve Test Sonuçları

```python
# Örnek 1: AŞTİ → OSB
rota = metro.en_az_aktarma_bul("M1", "K4")
# Çıktı: AŞTİ → Kızılay → Kızılay → Ulus → Demetevler → OSB

# Örnek 2: Batıkent → Keçiören
sonuc = metro.en_hizli_rota_bul("T1", "T4")
# Çıktı: (21 dakika) Batıkent → Demetevler → Gar → Keçiören

#### 🚇 🚀 Projeyi Geliştirme Fikirleri

    Gerçek Zamanlı Veri Entegrasyonu

        API ile canlı metro yoğunluk bilgisi

        Kesinti/arıza bildirimleri

    Gelişmiş Özellikler

        Engelli erişim filtresi

        "En ucuz rota" modu (bilet fiyatlarına göre)

    GUI Entegrasyonu

        Tkinter veya Flask ile web arayüzü

        Harita üzerinde rota görselleştirme

    Veri Yönetimi

        İstasyon verilerini CSV/JSON'dan okuma

        SQLite veritabanı entegrasyonu
