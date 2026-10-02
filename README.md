# Futbolcu Veri Madenciliği ve Makine Öğrenmesi

Bu proje, futbolcu ve kaleci performans verileri üzerinde **veri ön işleme, veri temizleme, aykırı değer analizi ve makine öğrenmesi sınıflandırma** adımlarını içeren bir Veri Madenciliği dersi çalışmasıdır.

> **Proje kurtarma notu:** Bilgisayara format atılması sonrasında orijinal proje dosyaları kaybolduğu için bu repo, daha önce alınmış Jupyter Notebook PDF çıktısı kullanılarak yeniden düzenlenmiştir. Ham veri seti şu anda repoya dahil değildir. Kod akışı ve aşağıda verilen model sonuçları, orijinal çalışma çıktısından alınmıştır.

## Proje Özeti

Orijinal çalışmada futbolcular ve kaleciler için ayrı veri setleri kullanılmış, eksik ve hatalı değerler temizlenmiş, veriler birleştirilmiş ve makine öğrenmesi modelleri ile oyuncu performans sınıflandırması yapılmıştır.

### Orijinal veri dosyaları

| Dosya | Boyut |
|---|---:|
| `player_predictions.csv` | 30.645 × 58 |
| `goalkeeper_predictions.csv` | 2.567 × 58 |
| `player_role_clusters.csv` | 11.273 × 18 |

Futbolcu ve kaleci verileri rol bazlı olarak düzenlendikten sonra veri seti **33.212 satır × 59 sütun** boyutuna ulaşmıştır.

## Uygulanan İşlemler

- Eksik veri analizi
- Futbolcu / kaleci rolüne göre veri temizleme
- `is_goalkeeper` özelliğinin oluşturulması
- Boy ve kilo bilgilerinin sayısal değerlere dönüştürülmesi
- Hatalı değerlerin düzeltilmesi
- Median ile eksik veri doldurma
- Min-Max normalizasyonu
- Z-score standardizasyonu
- Gereksiz sütunların çıkarılması
- IQR yöntemi ile aykırı değer tespiti
- Clipping ile aykırı değer temizleme
- Rolling median ile veri yumuşatma
- Quantile tabanlı sınıflandırma
- One-Hot Encoding
- Logistic Regression
- Random Forest
- Feature Importance analizi
- 5-Fold Cross Validation
- TAN Bayesian Network

## Proje Akışı

```text
Ham Futbolcu / Kaleci Verileri
        ↓
Eksik Veri Analizi
        ↓
Rol Bazlı Veri Temizleme
        ↓
Veri Setlerinin Birleştirilmesi
        ↓
Boy / Kilo Dönüşümü
        ↓
Eksik ve Hatalı Değerlerin Düzeltilmesi
        ↓
Normalizasyon / Standardizasyon
        ↓
Veri Azaltma
        ↓
IQR Aykırı Değer Analizi
        ↓
Veri Yumuşatma
        ↓
Ayrıklaştırma
        ↓
Makine Öğrenmesi Modelleri
```

## Model Sonuçları

Orijinal Jupyter Notebook çıktısında elde edilen sonuçlar:

| Model / Değerlendirme | Sonuç |
|---|---:|
| Logistic Regression test accuracy | **%70,37** |
| Random Forest test accuracy | **%85,79** |
| Random Forest 5-Fold CV ortalaması | **%63,96** |
| TAN Bayesian Network test accuracy | **%24,26** |

Random Forest modelinde öne çıkan özelliklerden bazıları:

- `minutes_played`
- `tackles_score`
- `duels_score`
- `discipline_score`
- `defensive_efficiency_per90`

## Kullanılan Teknolojiler

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- NetworkX
- pgmpy
- Jupyter Notebook

## Proje Yapısı

```text
football-player-data-mining/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── football_player_data_mining.ipynb
├── data/
│   └── README.md
└── report/
    └── original_project_report.pdf
```

## Veri Seti Hakkında

Ham veri seti şu anda mevcut değildir. Notebook'un çalışması için orijinal olarak aşağıdaki dosyaları içeren `archive.zip` kullanılmıştır:

```text
player_predictions.csv
goalkeeper_predictions.csv
player_role_clusters.csv
```

Veri seti daha sonra bulunursa:

```text
data/archive.zip
```

konumuna eklenerek notebook yeniden çalıştırılabilir.

## Çalıştırma

Gerekli kütüphaneler:

```bash
pip install -r requirements.txt
```

Daha sonra Jupyter Notebook veya Google Colab üzerinden:

```text
notebooks/football_player_data_mining.ipynb
```

dosyası açılabilir.

> Ham veri seti mevcut olmadığı için repo şu anda uçtan uca yeniden çalıştırılamaz. Notebook'taki yöntemler ve belirtilen sonuçlar, orijinal proje çıktısından kurtarılmıştır.

## Geliştirici

**Kaan Kuzucanlı**  
Bilgisayar Mühendisliği
