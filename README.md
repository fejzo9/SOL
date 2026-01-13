# Samoorganizirajuće liste: Wikipedia Pageviews (NASP projekat)

Ovaj repozitorij sadrži Jupyter notebook za implementaciju i eksperimentalnu evaluaciju samoorganizirajućih lista (Self-Organizing Lists, SOL) nad realnim podacima pristupa sa Wikipedia pageviews (01.01.2024.).

Fokus je na poređenju klasičnih heuristika:

- **Move-to-Front (MTF)**
- **Transpose (TR)**
- **Count (CNT)**

nad velikim nizom pristupa člancima (heavy-tailed / Zipfova distribucija, visok entropijski workload).

---

## Struktura repozitorija

- `NASP_lab_Wikipedia_PageViews.ipynb`  
  Glavni notebook koji sadrži:
  - učitavanje i pripremu niza pristupa (access sequence),
  - implementacije MTF, TR i CNT heuristika,
  - računanje ukupnog i prosječnog troška po pristupu,
  - osnovne grafove i tabelarni prikaz rezultata.

---

## Zahtjevi

Za pokretanje je potreban **Python 3.9+** i sljedeće biblioteke:

- `numpy`
- `pandas`
- `matplotlib`
- (opcionalno) `tqdm` za progres bar

Instalacija (preporučeno u virtualnom okruženju):

```bash
pip install numpy pandas matplotlib tqdm
```

---

## Pokretanje

1. Kloniraj ili preuzmi repozitorij:
   ```bash
   git clone <URL_REPOZITORIJA>
   cd <NAZIV_REPOZITORIJA>
   ```

2. Pokreni Jupyter:

   ```bash
   jupyter notebook
   ```

3. Otvori `NASP_lab_Wikipedia_PageViews.ipynb` i izvrši ćelije redom (od vrha do dna).

Ako koristiš vlastiti dataset, prilagodi putanju do fajla u ćeliji za učitavanje podataka.

---

## Eksperimentalni rezultati (sažetak)

Glavni ciljevi eksperimenta:

- uporediti **ukupan trošak** i **prosječan trošak po pristupu** za MTF, TR i CNT,
- analizirati ponašanje heuristika na velikom, nestacionarnom, heavy-tailed nizu (Wikipedia pageviews),
- pokazati da MTF u praksi značajno nadmašuje CNT i TR na ovom tipu workload-a.

Primijećeno je:

- MTF agresivno koristi lokalitet reference i postiže znatno niži prosječni trošak,
- CNT i TR pokazuju visok prosječan trošak na istom nizu, posebno kako broj pristupa raste,
- linearna pretraga postaje usko grlo za liste sa stotinama hiljada elemenata, što motiviše naprednije strukture (Lists-on-Lists, konkurentne/lock-free varijante).

Više detalja, formalni teorijski okvir i literatura nalaze se u pratećem radu pisanom u LaTeX-u.

---

## Autori

- **Esma Dizdarević** – Elektrotehnički fakultet, Univerzitet u Sarajevu  
- **Fejzullah Ždralović** – Elektrotehnički fakultet, Univerzitet u Sarajevu
