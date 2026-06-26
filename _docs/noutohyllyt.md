---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/noutohyllyt/
redirect_from:
  - /theme-setup/
toc: true
---

Tässä ohjeessa on neuvottu pääkäyttäjille, miten varausten noutohyllyt voidaan ottaa Kohassa käyttöön. Käyttäjille suunnattu ohje noutohyllyistä löytyy [täältä](https://koha-suomi.fi/dokumentaatio/varaukset/#43-noutohyllyt).

## Järjestelmäasetukset

Mene Ylläpito -> Järjestelmäasetukset

Asetuksen nimi|Valinta|Selite
---|---|---
HoldPickupShelves |Ota käyttöön |Kytkee noutohyllyt päälle (ei tee kuitenkaan vielä yksistään mitään, vaan kirjastoille on lisäksi määriteltävä noutohyllyt)
HoldPickupShelvesBiblioLevelItemTypeParameter |MTYPE |Määrittelee, että käytetään MTYPE-aineistotyyppejä noutohyllyjen asetuksissa

## Noutohyllyjen määrittely

Mene Ylläpito -> Varausten noutohyllyt

Noutohylly-toiminnallisuus edellyttää, että kirjastolle on määritelty noutohyllyjä. Jos noutohyllyjä ei ole, toimii kyseisen kirjaston varausten osalta käsittely ”vanhaan tapaan” eli tärppäyttäessä ei valita noutohyllyä vaan ainoastaan vahvistetaan varaus noudettavaksi/kuljetettavaksi.

Noutohyllylle on aina määriteltävä kirjasto, nimi sekä noutohyllyyn mahtuva nidemäärä.

Noutohyllyn voi halutessaan sitoa tiettyyn viikonpäivään, aineistotyyppiin ja asiakastyyppiin.

Noutohyllyn voi myös lukita pois käytöstä tai määrittää ylivuotohyllyksi, jolloin Koha ei tarjoa noutohyllyä elleivät kaikki muut noutohyllyt ole jo käytössä. Pääkäyttäjä pystyy myös poistamaan lukituksen, jos jokin hylly on esimerkiksi vahingossa merkattu täydeksi ja se haluttaisiin takaisin saataville.

- **Huom!** Tyhjentynyt, 0 nidettä sisältävä noutohylly voi näkyä ylläpidon puolella lukittuna, vaikka se ei todellisuudessa sitä ole. Tämä johtuu siitä, että lukitus-rasti poistuu noutohyllyn tiedoista vasta kun toimipisteessä tärppäytetään ensimmäinen varaus tyhjentymisen jälkeen. Koha osaa siis tarjota tyhjentyneitä noutohyllyjä välittömästi vaikka ylläpidossa vielä lukitus-rasti olisikin. Tyhjän hyllyn lukitusta *ei* kannata mennä sörkkimään, sillä ainakin Turussa saatiin tällä tavoin aikaan tilanne jossa hyllyt eivät vapautuneetkaan käytettäväksi ilman kehittäjän tekemää tietokanta-ajoa.

Noutohyllyn nimen ei tarvitse olla uniikki, mutta tismalleen kahta samanlaista noutohyllyä ei voi luoda.

Noutohyllyjen prioriteettijärjestystä voi säätää nuolipainikkeilla ja pudotusvalikosta arvon valitsemalla. Jotta säätämistä olisi mahdollisimman vähän, kannattaa perustamisvaiheessa miettiä jo valmiiksi missä järjestyksessä noutohyllyt perustaa.

- Huom! Suodata näkyville haluamasi kirjaston noutohyllyt, kun alat muokata prioriteettijärjestystä. Mikäli prioriteettinä näkyy aluksia kaikille '1', päivittyvät prioriteettiarvot ajan tasalle, kun muokkaat jonkin noutohyllyn prioriteettiä.

## Esimerkki noutohyllylogiikasta ja järjestyksestä Turussa

Prioriteetti|Kirjaston nimi|Hyllyn nimi|Niteitä enintään|Viikonpäivä|Asiakastyyppi|Aineistotyyppi|Ylivuotohylly|Lukittu
---|---|---|---|---|---|---|---|---
1 |Turku, Varissuon kirjasto |Kaukolaina-01 |99 | |Kaukolainakirjasto |Mikä tahansa |Ei |Ei
2 |Turku, Varissuon kirjasto |Kaukolaina-02 |99 | |Kaukolainakirjasto |Mikä tahansa |Ei |Ei
3 |Turku, Varissuon kirjasto |Kaukolaina-03 |99 | |Kaukolainakirjasto |Mikä tahansa |Ei |Ei
4 |Turku, Varissuon kirjasto |Työkortti-01 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
5 |Turku, Varissuon kirjasto |Työkortti-02 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
6 |Turku, Varissuon kirjasto |Työkortti-03 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
7 |Turku, Varissuon kirjasto |Työkortti-04 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
8 |Turku, Varissuon kirjasto |Työkortti-05 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
9 |Turku, Varissuon kirjasto |Työkortti-06 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
10 |Turku, Varissuon kirjasto |Työkortti-07 |99 | |Ei-tilastoitavat lainat |Mikä tahansa |Ei |Ei
11 |Turku, Varissuon kirjasto |Kotipalvelu-01 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
12 |Turku, Varissuon kirjasto |Kotipalvelu-02 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
13 |Turku, Varissuon kirjasto |Kotipalvelu-03 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
14 |Turku, Varissuon kirjasto |Kotipalvelu-04 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
15 |Turku, Varissuon kirjasto |Kotipalvelu-05 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
16 |Turku, Varissuon kirjasto |Kotipalvelu-06 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
17 |Turku, Varissuon kirjasto |Kotipalvelu-07 |99 | |Kotipalveluasiakas |Mikä tahansa |Ei |Ei
18 |Turku, Varissuon kirjasto |A16 |5 | |Mikä tahansa |LAUTAPELI |Ei |Ei
19 |Turku, Varissuon kirjasto |B16 |5 | |Mikä tahansa |LAUTAPELI |Ei |Ei
20 |Turku, Varissuon kirjasto |C16 |5 | |Mikä tahansa |LAUTAPELI |Ei |Ei
21 |Turku, Varissuon kirjasto |D16 |5 | |Mikä tahansa |LAUTAPELI |Ei |Ei
22 |Turku, Varissuon kirjasto |A19 |5 | |Mikä tahansa |LAUTAPELI |Ei |Ei
23 |Turku, Varissuon kirjasto |B19 |5 | |Mikä tahansa |LAUTAPELI |Ei |Ei
24 |Turku, Varissuon kirjasto |A1 |15 | |Mikä tahansa |Mikä tahansa |Ei |Ei
25 |Turku, Varissuon kirjasto |A2 |15 | |Mikä tahansa |Mikä tahansa |Ei |Ei
26 |Turku, Varissuon kirjasto |A6 |15 | |Mikä tahansa |Mikä tahansa |Ei |Ei
27 |Turku, Varissuon kirjasto |A7 |15 | |Mikä tahansa |Mikä tahansa |Ei |Ei
28 |Turku, Varissuon kirjasto |B1 |15 | |Mikä tahansa |Mikä tahansa |Ei |Ei
29 |Turku, Varissuon kirjasto |B2 |15 | |Mikä tahansa |Mikä tahansa |Ei |Ei

(Jne, kaikki loput hyllyt siis tavallisia noutohyllyjä, joissa ei ole mitään asiakas- tai aineistotyyppirajausta.)


## Viesti- ja kuittipohjat

Varauskuitti (HOLD_SLIP), saapumisilmoitus (HOLD) ja noutomuistutus (HOLD_REMINDER) -pohjiin on lisättävä noutohylly-tieto. Seuraavalla Template Toolkit -rimpsulla pohjiin on mahdollista määritellä tulostumaan ensisijaisesti noutohyllytieto ja jos sitä ei löydy, asiakkaan varaustunniste:

```
[% IF hold.hold_pickup_shelf_id %]<<hold_pickup_shelf>>[% ELSE %]<<borrower-attribute:HOLDID>>[% END %]
```

Halutessasi voit myös lisätä uuden räätälöidyn kuittipohjan, jolla asiakkaan tiedoista saa tulostettua kuitin noudettavissa olevista varauksista. [Mallipohja löytyy viesti- ja kuittipohjakirjastosta.](https://koha-suomi.fi/dokumentaatio/kuititjaviestit/#r%C3%A4%C3%A4t%C3%A4l%C3%B6ity-kuitti-asiakkaan-noudettavat-varaukset)

## Raportit

Noutamattomien erääntyneiden varausten raportille on lisättävä noutohyllytieto. [Esimerkki Turun raportista, johon noutohyllytieto on lisätty, löytyy raporttikirjastosta.](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#vanhentuneet-noutamattomat-varaukset-raportilla-noutohylly-tieto)

Kannattaa tarkistaa myös onko muita tallennettuja raportteja, joihin noutohylly pitäisi saada näkyville.

## Taulujen asetukset

Lisää palautusnäkymään näkyville noutohylly-sarake (Ylläpito -> Taulujen asetukset -> Lainaus ja palautus -> returns -> pickup_shelf).

## Verkkokirjasto (Finna)

Verkkokirjastoon noutohyllytieto on mahdollista saada näkyville asiakkaan Varaukset-sivulle. Pyydä Finna-toimistoa tekemään muutos. Noutohylly näytetään noudettavissa-tiedon alapuolella.

![](/assets/files/docs/Varaukset/Verkkokirjasto_noutohylly.png)

Kannattaa myös tarkistaa, onko verkkosivuilla muualla (esim. Asiakkaan ohjeissa) tarvetta päivittää tietoja varaustunnisteeseen liittyen.
