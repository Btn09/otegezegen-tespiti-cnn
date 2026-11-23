# Yapay Sinir Ağlarıyla Ötegezegen Tespiti

Batın Dikilitaş · 240121001 · Yapay Sinir Ağları

Kepler teleskobunun ışık eğrilerinden gezegen sinyallerini ayırt eden bir 1D CNN.

## Kurulum

```
pip install -r requirements.txt
```

## Çalıştırma

```
jupyter notebook otegezegen_tespiti.ipynb
```

Sonra menüden *Run All*.

- `kepler_veri/tfrecord/` : Shallue ve Vanderburg (2018) tarafından işlenmiş Kepler DR24 sinyalleri (yaklaşık 145 MB). Yoksa notebook Google Drive'dan indiriyor.
- `kepler_veri/kepler90.npz` : Kepler-90'ın NASA MAST'tan indirilmiş ışık eğrisi. Yoksa notebook lightkurve ile indiriyor.
- `sonuclar/model.keras` : eğitilmiş model. Notebook'taki `YENIDEN_EGIT = False` iken bu model yükleniyor; `True` yapılırsa ağ baştan eğitiliyor (yaklaşık 2 dakika, CPU).
- `sonuclar/*.png` : notebook'un ürettiği grafikler.

Veri ve model dosyaları yerinde olduğu sürece internet bağlantısı gerekmiyor.

## Test seti sonuçları

| Ölçüt | Değer |
| --- | --- |
| Doğruluk | 0,959 |
| Kesinlik | 0,866 |
| Duyarlılık | 0,972 |
| F1 skoru | 0,916 |
| ROC AUC | 0,988 |
