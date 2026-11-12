# Polazni i pripremljeni skupovi

Izvor je [Kaggle skup Credit Card Transactions Fraud Detection](https://www.kaggle.com/datasets/kartik2112/fraud-detection), preuzet lokalno kao `fraudTrain.csv`. Datoteka sadrži 1.296.675 transakcija i 7.506 prevara. Zbog veličine od oko 335 MiB izvorni CSV nije dio Git verzije; za reprodukciju uzorkovanja preuzima se s Kagglea u korijenski direktorij. Bilježnica iz njega reprodukuje dva CSV skupa:

- `fraud_balanced.csv`: svih 7.506 prevara i nasumično odabranih 7.506 legitimnih transakcija (`random_state=42`), ukupno 15.012 redova.
- `fraud_15k.csv`: stratifikovani uzorak od 15.000 redova, sa 14.913 legitimnih i 87 prevarnih transakcija.

Za svaki CSV postoji pripremljena datoteka: `fraud_balanced_prepared.npz` i `fraud_15k_prepared.npz`. Svaka sadrži cijeli skup bez podjele, kodiranu rijetku CSR matricu od 1.026 kolona, cilj `y`, oznake transakcija, nazive kolona te numeričke i kategoričke ulaze prije standardizacije i one-hot kodiranja.

Obje datoteke su potrebne za kasniju obradu balansirane i nebalansirane verzije po istim pravilima. Za učenje modela koristite sačuvane `numeric_values` i `categorical_values`: podatke prvo podijelite, zatim grupisanje rijetkih kategorija, imputaciju, one-hot kodiranje i skaliranje prilagodite trening dijelu i istim parametrima obradite ostale dijelove. CSR matrica je zajednički prikaz za pripremu i poređenje kolona; pretprocesor koji ju je napravio prilagođen je uniji jedinstvenih transakcija.

Primjer čitanja:

```python
import numpy as np

path = 'pripremljeni_podaci/fraud_balanced_prepared.npz'
with np.load(path, allow_pickle=False) as data:
    y = data['y']
    trans_num = data['trans_num']
    feature_names = data['feature_names']
    numeric_values = data['numeric_values']
    numeric_columns = data['numeric_columns']
    categorical_values = data['categorical_values']
    categorical_columns = data['categorical_columns']
```
