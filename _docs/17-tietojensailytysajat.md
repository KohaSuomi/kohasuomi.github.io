---
title: 'Tietojen säilytysajat'
permalink: /dokumentaatio/tietojensailytysajat/
redirect_from:
  - /theme-setup/
toc: true
---

## Asiakastietoihin liittyvät siivousajot

### Asiakkaan viestit (tekstiviestit, sähköpostit, e-kirjeet) 

Asiakkaille lähetetyt viestit message_queue-taulussa, jotka näkyvät asiakkaan tiedoissa Ilmoitukset-välilehdellä.
* **Päätös**: kuluva + 3 vuotta: kuluva vuosi + 1 vuosi aktiivisessa taulussa, loput vuositauluissa. Ajo joka kuun eka päivä.
  * ODUECLAIM eli laskut säilytettävä 10 vuotta aktiivisessa taulussa, jotta laskutustyökalu saa haettua tarvittaessa tiedot laskujäljennöksiä varten
 

### Vanhat istunnot

Koha-käyttäjätunnusten kirjautumiset Kohaan.

* **Päätös**: Poistetaan joka yö voimassa olevat 

### Vanhentuneet maksut

Kohan accountlines-taulusta vanhentuneet maksut pois.

* **Päätös:** maksamattomat/voimassa olevat maksut
  * Yksityisoikeudelliset: itse lisäsyt esim. kopiomaksut, korvaushinnat 3 vuotta
  * Julkisoikeudelliset: esim. myöhästymismaksut 5 vuotta

### Poistetut asiakastietueet

Kohan deleted_borrowers-taulusta pois vanhemmat tiedot.

* **Päätös:** Säilytetään 1 kk 
  * ajo joka yö


### Ei-aktiiviset asiakastiedot

Esimerkiksi vanhentuneet asiakastilit, borrowers-taulu.

* **Päätös**: Kimppakohtainen säilytysaika. Ajetaan kerran vuodessa.  

### Lainahistoria

Kohan old_issues-taulu. Lainahistorian voi määrittää säilymään kolmella tavalla aina/default(kirjaston määrittämän ajan)/heti poistuu. Tässä määritetään default. 

* Lainat ja palautukset kirjautuvat myös statistics-tauluun. Miten huolehditaan pitkäaikainen lainatilastojen säilyminen työkäyttöä varten? 
* termimuutos: aina -> toistaiseksi

* **Päätös:** default 3 vuotta
  * Tiedotus Finnoihin, mitä säilytysajat ovat ja mahdollisuus vaihtaa toistaiseksi-vaihtoehdoksi ennen kuin ajetaan lainahistorioita pois.


### Käsitellyt varaukset

Kohan old_reserves-taulu.

* **Päätös**: 3 vuotta
  * Noudattaa asiakkaan lainahistoria-valintaa

### Tilastotaulu

Kohan statistics-taulu.

* **Päätös**: Säilytetään toistaiseksi, mutta aktiivisessa statistics-taulussa vain kuluva + 1 vuosi. Loput siirretään "vuositauluihin", statistics_2018, statistics_2019 jne.
  * Kirjaus Asiantuntijaryhmän muistio 10/23: kuluva + vuosi, ajo tammikuussa

### Hakuhistoria

Hakuhistoria löytyy Kohan käyttöliittymästä oikean yläreunan valikosta.

* **Päätös**: 1 kk

### Tapahtumalokit

Kohan action_logs-taulu.

* **Päätös**: Säilytetään toistaiseksi, mutta aktiivisessa action_logs -taulussa 12 kk, ajo joka kuun eka päivä. Loput siirretään vuositauluihin, action_logs_2018, action_logs_2019 jne.

### Poistetut niteet ja tietueet 

Kohassa items-, biblio-, biblioitem- sekä biblio_metadata-taulut.

* **Päätös**: 5 vuotta

### Hankintasanomien käsittelytiedot

Kohassa edifact_messages-taulu.

* **Päätös:** 1 vuosi

### Taustatyöt

Kohassa background_jobs-taulu.

* **Päätös:** 1 kk, ajetaan päivittäin

### Niteiden kuljetukset

Kohassa branchtransfers-taulu.

* Pääkäyttäjäryhmän päätös 4.10.2022: Säilytetään 2 vuotta
* **Päätös:** 2 vuotta, ajetaan joka kuun 1. päivä
