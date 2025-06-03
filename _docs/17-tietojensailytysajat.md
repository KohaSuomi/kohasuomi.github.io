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
* Tieteelliset säilyttää 3 vuotta 
* Ongelmien selvittelyn kannalta hyvä säilyttää vähän pidempi aika
* **Päätös**: kuluva + 3 vuotta: kuluva vuosi aktiivisessa taulussa, loput vuositauluissa
  * ODUECLAIM eli laskut säilytettävä 10 vuotta
*  Kirjaus Asiantuntijaryhmän muistio 10/2023: 12 kk, ajo joka kuun eka päivä 

### Vanhat istunnot

Koha-käyttäjätunnusten kirjautumiset Kohaan.

* **Päätös**: Poistetaan joka yö voimassa olevat
  * Selvitettävä: Itsepalvelulainauksen sessiot pysyttävä?

### Vanhat maksut (maksetut) 

Kohan accountlines-taulusta vanhat maksetut maksut pois.

* Tieteelliset säilyttää 3 vuotta 
* **Päätös:** maksamattomat/voimassa olevat maksut
  * Yksityisoikeudelliset: itse lisäsyt esim. kopiomaksut, korvaushinnat 3 vuotta
    * osa kimpoista katkaisee vanhentumisen huomauttamalla maksuista asiakasta. Kirjataan tikettiin, mille kimpoille tätä ei tehdä. (emaileri-liitännäisellä muistutus maksuista?)
  * Julkisoikeudelliset: esim. myöhästymismaksut 5 vuotta

### Poistetut asiakastietueet

Kohan deleted_borrowers-taulusta pois vanhemmat tiedot.

* **Päätös:** Säilytetään 1 kk 
  * ajo joka yö


### Ei-aktiiviset asiakastiedot

Esimerkiksi vanhentuneet asiakastilit, borrowers-taulu.

* **Päätös**: Last seen -arvo borrowers-taulussa pitää saada päivittymään ennen kuin poisto-ajoja voidaan tehdä. Kimppakohtainen säilytysaika. Ajetaan päivittäin?
  * Aktiiviset säilytetään 10 vuotta, kuten asiantuntijaryhmässä on päätetty 9.5.2022 kokouksessa 4/22.

### Lainahistoria

Kohan old_issues-taulu. Lainahistorian voi määrittää säilymään kolmella tavalla aina/default(kirjaston määrittämän ajan)/heti poistuu. Tässä määritetään default. 

* Lainat ja palautukset kirjautuvat myös statistics-tauluun. Miten huolehditaan pitkäaikainen lainatilastojen säilyminen työkäyttöä varten? 
* Tieteelliset säilyttää 3 vuotta 
* uudemmassa versiossa pseudonymisointi, tutkittava sen mahdollisuudet
* termimuutos: aina -> toistaiseksi

* **Päätös:** default 3 vuotta
  * Tiedotus Finnoihin, mitä säilytysajat ovat ja mahdollisuus vaihtaa toistaiseksi-vaihtoehdoksi ennen kuin ajetaan lainahistorioita pois.


### Käsitellyt varaukset

Kohan old_reserves-taulu.

* Tieteelliset säilyttää 3 vuotta
* **Päätös**: 2 vuotta

### Tilastotaulu

Kohan statistics-taulu.

* Tieteelliset säilyttää 2 vuotta
  * **Päätös**: Säilytetään toistaiseksi, mutta aktiivisessa statistics-taulussa vain kuluva + 1 vuosi. Loput siirretään "vuositauluihin", statistics_2018, statistics_2019 jne.
  * Kirjaus Asiantuntijaryhmän muistio 10/23: kuluva + vuosi, ajo tammikuussa

### Hakuhistoria

Hakuhistoria löytyy Kohan käyttöliittymästä oikean yläreunan valikosta.

* **Päätös**: 1 kk

### Tapahtumalokit

Kohan action_logs-taulu.

* Tieteelliset säilyttää 2 vuotta
* **Päätös**: Säilytetään toistaiseksi, mutta aktiivisessa action_logs -taulussa vain kuluva +1 vuosi. Loput siirretään vuositauluihin, action_logs_2018, action_logs_2019 jne.
* Kirjaus Asiantuntijaryhmän muistio 10/23: 12 kk aktiivisessa taulussa, ajo joka kuun eka päivä

### Poistetut niteet ja tietueet 

Kohassa items-, biblio-, biblioitem- sekä biblio_metadata-taulut.

* Tieteelliset säilyttää 5 vuotta
* mitä tehdään sitten jos maksuhistoriassa tietoa teoksista, jotka jo poistettu myös deletedbiblio-taulusta?
* **Päätös**: 5 vuotta

### Hankintasanomien käsittelytiedot

Kohassa edifact_messages-taulu.

* **Päätös:** 1 vuotta.

### Taustatyöt

Kohassa background_jobs-taulu.

* **Päätös:** 1 kk, ajetaan päivittäin

### Niteiden kuljetukset

Kohassa branchtransfers-taulu.

* Pääkäyttäjäryhmän päätös 4.10.2022: Säilytetään 2 vuotta
* **Päätös:** 2 vuotta
