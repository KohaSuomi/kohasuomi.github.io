---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/kaukolainaus/
redirect_from:
  - /theme-setup/
toc: true
---

## Kaukolainamoduulin käyttöönotto

### Järjestelmäasetukset

Mene Ylläpito ->  Järjestelmäasetukset -> Kaukolainat

Asetuksen nimi|Valinta|Selite
---|---|---
ILLDefaultStaffEmail |Jätä tyhjäksi|Ei tarpeen
ILLSendStaffNotices |Jätä tyhjäksi|
CirclulateILL|Älä salli/Salli|Tämä sallii lainaamisen suoraan kaukolainapyynnön kautta ilman että mennään asiakkaan tietoihin ja manuaalisesti luetaan niteen viivakoodi. Tämä luo automaattisesti niteen ja sille viivakoodin.
ILLHiddenRequestStatuses ||
ILLModule |Käytä|Tämä on ns. pääkytkin, jolla Kaukolaina-toiminto kytketään päälle ja pois päältä.
ILLModuleUnmediated |Älä salli|Vaatii toimiakseen Kohan oma verkkokirjaston (opac)
ILLPartnerCode|Kaukolainakirjasto-asiakastyyppi|Tämä tuo kaukolainapyynnön lähetykseen näkyville Kaukolainakirjasto-tyyppiset asiakastiedot, joilla on tiedoissaan sähköpostiosoite tallennettuna
ILLCheckAvailability |Älä tarkista|Ei tarpeen, koska meillä ei ole tähän tarvittavia yhteyksiä
ILLModuleDisclaimerByType|Jätä tyhjäksi|
ILLOpacbackends |Jätä tyhjäksi|Vaatisi toimiakseen Kohan oman verkkokirjaston (opacin)

### Auktorisoidut arvot

ILL_STATUS_ALIAS -auktorisoitu arvo

* Saapunut
* Noutoilmoitus lähetetty
* Noutamaton kaukolaina
* Asiakas perunut pyynnön
* Lainattu asiakkaalle (jos nide lisätään itse ja lainataan Kohan normaalin lainauksen kautta, ei tieto päivity Kaukolainamoduulin puolelle)
* Karhuttu



### Nidetyyppi

Tunnus: KAUKOLAINA<br />
Kuvaus: Kaukolaina<br />
Palautusviesti: Tähän jonkinlainen huomautus, että kyseessä on kaukolaina ja tarvitsee erilaista käsittelyä<br />
Palautusviestin tyyppi: Huomautus (tulee keltaisella pohjalla oleva huomautus palautuksessa, erottuu paremmin kuin viesti)

### Käyttäjäoikeudet

* ill - jotta pääsee kaukopalvelumoduuliin
* fast_cataloging  - jotta pystyy käsittelemään kaukolainamoduulin kautta luotuja tietueita/niteitä, joilla on FA-kuvailupohja käytössä
* override_renewals - jotta käyttäjä pystyy tarvittaessa ohittamaan nidetyypille asetetun uusintojen määrän 0
* overdues_report - jotta käyttäjä voi avata Myöhässä-raportin Lainaus ja palautus -sivulla

### Laina- ja maksusäännöt

* Asiakastyyppi: Ei tarvitse valita, koska säännöt ovat samat kaikille asiakastyypeille
* Nidetyyppi: Kaukolaina
* Sallittu lainamäärä: kimpan käyttösääntöjen mukaisesti
* Laina-aika: 28 vrk - tähän kannattanee määrittää jotain, koska muuten Koha automaattisesti antaa eräpäiväksi lainauspäivän. Pääsääntöisesti virkailija valitsee itse eräpäivän sen mukaan, mitä lähettävä kirjasto on sen määrittänyt.
* Uusintakerrat: 0, jotta asiakkaat eivät pysty uusimaan lainojaan verkkokirjastossa. Annetaan kuitenkin kaukopalvelua tekeville henkilöille käyttäjäoikeus, jolla he voivat ohittaa uusinnan estot.
* Uusinta-aika: 28 vrk samalla perusteella kuin laina-aika. Uusinnan eräpäivän voi valita lainat-taulukon alapuolelta.
* Ei uusintaa ennen: kimppakohtaisesti päätettävissä
* Varauksia sallittu (yhteensä): 0
* Varauksia sallittu (päivittäin): 0
* Varauksia tietuetta kohti (määrä): 0
* Hyllyvaraukset sallittu: Jos yhtään ei ole saatavilla
* Verkkokirjaston nidevaraukset: Älä salli

Oletusvaraussääntö nidetyypeittäin
 * tänne voi tarvittaessa lisätä palautussäännön Kaukolaina-nidetyypille, että se palaa lainaavaan (tilaavaan) kirjastoon tai kotikirjastoon, jolloin se käytännössä palautuu kaukolainan tilanneeseen kirjastoon.

Jos jollakin kirjastolla on kirjastokohtaisia lainasääntöjä, pitää nämä muistaa tehdä kaikille kirjastoille, joihin säännöt halutaan "purevan".

Jos kimpassa on asiakastyyppejä, joille ei haluta sallia kaukolainojen lainaamista, pitää asiakastyypille tehdä sääntö, jossa lainamäärä on 0.

### Viestipohjat ja uudet viestiasetukset

#### Viestiasetukset

#### Viestipohjat

##### ILL_REQUEST_UPDATE

Vain email-tyyppinen viesti, ei haluta lähettää tekstiviestinä.

Viestin otsikko: Kaukolainapyyntöäsi on päivitetty
Viestityyppi: email

```
Hei [% borrower.firstname %],

kaukolainapyyntöäsi  [% ill_bib_title %] / [% ill_bib_author %] on päivitetty.

Päivitetyt tiedot:

[% additional_text %]

Ystävällisin terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

##### ILL_PICKUP_READY

Otsikko: Kaukolainan noutoilmoitus
Viestityyppi: email

```
Hei [% borrower.firstname %],

Pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] on noudettavissa [% branch.branchname %]sta.

Kaukolainamaksu: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %] 
Eräpäivä: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]

Terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

Otsikko: Kaukolainan noutoilmoitus
Viestityyppi: sms

```
Pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] on noudettavissa [% branch.branchname %]sta. Kaukolainamaksu: [% IF illrequest.price_paid %][% illrequest.price_paid %][% ELSE %]8 €[% END %]. Eräpäivä: [% IF illrequest.notesstaff %][% illrequest.notesstaff %][% ELSE %]-[% END %]
```

##### ILL_PARTNER_REQ

Otsikko: Kaukolainapyyntö
Viestityyppi: email

```
Hei,

pyytäisimme kaukolainaksi seuraavan teoksen:

[% ill_full_metadata %]

Ystävällisin terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
```

##### ILL_REQUEST_UNAVAIL

Otsikko: Pyytämäsi kaukolaina ei ole saatavilla
Email:
```
Hei [% borrower.firstname %],

pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] ei ole saatavilla.


Terveisin

[% branch.branchname %]
[% branch.branchaddress1 %]
[% branch.branchzip %] [% branch.branchcity %]
[% branch.branchphone %]
[% branch.branchillemail %]
[% branch.branchemail %]
```

Otsikko: Kaukolaina ei saatavilla
Viestityyppi: Sms

```
Hei [% borrower.firstname %],  pyytämäsi kaukolaina [% ill_bib_title %] / [% ill_bib_author %] ei ole saatavilla. Terveisin [% branch.branchname %]
```

### FA-kuvailupohja

942n=1 estää tietueen näkymisen verkkokirjastossa eli sen voisi laittaa kaukolainojen käyttämän Fast Add -kuvailupohjan oletusarvoksi

### Raportit

* myöhässä olevia kaukolainoja voi seurata Overdues-raportilla (joka on tällä hetkellä piilotettu kaikilla Lainaus ja palautus -sivulla) (vaatii overdues_report-oikeuden)

### Kuinka asiakkaat tekevät kaukolainapyyntöjä

