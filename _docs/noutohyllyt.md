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

Noutohyllyn voi myös lukita pois käytöstä tai määrittää ylivuotohyllyksi, jolloin Koha ei tarjoa noutohyllyä elleivät kaikki muut noutohyllyt ole jo käytössä.

Noutohyllyn nimen ei tarvitse olla uniikki, mutta tismalleen kahta samanlaista noutohyllyä ei voi luoda.

Noutohyllyjen prioriteettijärjestystä voi säätää nuolipainikkeilla ja pudotusvalikosta arvon valitsemalla. Jotta säätämistä olisi mahdollisimman vähän, kannattaa perustamisvaiheessa miettiä jo valmiiksi missä järjestyksessä noutohyllyt perustaa.

- Huom! Suodata näkyville haluamasi kirjaston noutohyllyt, kun alat muokata prioriteettijärjestystä. Mikäli prioriteettinä näkyy aluksia kaikille '1', päivittyvät prioriteettiarvot ajan tasalle, kun muokkaat jonkin noutohyllyn prioriteettiä.

## Esimerkki noutohyllylogiikasta ja järjestyksestä Turussa

(Tähän lisätään esimerkki myöhemmin, kun noutohyllyt on saatu kunnolla Turussa käyttöön)

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
