---
title: 'Käyttöönotto-ohjeita'
permalink: /dokumentaatio/kayttoonotto-ohjeita/
redirect_from:
  - /theme-setup/
toc: true
---

Tälle sivulle on kerätty erilaisia käyttöönotto-ohjeita. Katso myös [uusien integraatioiden käyttönotto-ohje](/dokumentaatio/uudet_integraatiot/).

## Asteri-liitännäinen

Asteri-liitännäisellä saa haettua Kansalliskirjaston KANTO-tietokannasta auktoriteettitietueita TäTiin.

[Asteri-liitännäisen käyttöönotto-ohje](/dokumentaatio/asteri/)

## EDItX-hankinta

[EDItX-hankinnan käyttöönotto-ohje](/dokumentaatio/editx/)

## Finto-liitännäiset

Finto-liitännäisiä voi hakea auktorisoituja muotoja käytettävistä termeistä Finton-rajapinnan kautta. Liitännäiset ovat käytössä TäTi-tietokannassa.

[Finto-liitännäisten määrittely](/dokumentaatio/finto/)

## Laskutustyökalu

Laskutustyökalu on toteutettu liitännäisenä.

[Laskutustyökalun käyttöönotto-ohje](https://github.com/KohaSuomi/koha-plugin-overdue-tool/wiki) Koha-Suomen GitHubissa.

## Nidetyypin automaattinen generointi

Koha-Suomessa on tehty liitännäinen _itemtype.pl_, jolla pystyy generoimaan automaattisesti niteelle nidetyypin. Liitännäinen hakee tietokannasta samoilla ehdoilla olevia niteitä ja tutkii, mikä nidetyyppi on suosituin vastaavilla niteillä. Sitten se ehdottaa samaa suosituinta nidetyyppiä uudelle/muokattavalle niteelle. Valinta tehdään aineistotyypin, hyllypaikan, hyllytarkenteen ja kokoelmakoodin perusteella.

Liitännäisen saa käyttöön Ylläpidossa MARC-kuvailupohjien ylläpidossa. Liitännäinen pitää määrittää käyttöön erikseen kaikille halutuille kuvailupohjille.

1. Valitse halutun kuvailupohjan kohdalla Toiminnot -> MARC-rakenne
2. Hae esille kenttä 952 ja valitse Toiminnot -> Näytä osakentät
3. Muokkaa osakenttää 952$y eli Kohan nidetyyppi
4. Ota pois valinta Auktorisoitu arvo -valikosta (siinä on todennäköisesti valittuna itemtypes)
5. Valitse Liitännäinen-valikosta _itemtype.pl_-vaihtoehto
6. Tallenna muutokset
7. Toista kohdat 1-6 kaikille halutuille kuvailupohjille

[Kuvaus liitännäisen toiminnasta](https://koha-suomi.fi/dokumentaatio/kuvailu/#5212-nidetyypin-automaattinen-generointi) Kohan ohje suomeksi -ohjeessa.

## Palautuskehotukset ensisijaisesti sähköpostina


Kun halutaan lähettää palautuskehotukset ensisijaisesti sähköpostiin ja kirjeenä vain niille, joilla ei ole sähköpostiosoitetta, voidaan tämä toteuttaa seuraavasti:

Mene myöhästymisilmoitusten määrittelyyn ja laita täpät kohtiin _Sähköposti_ ja _Tuloste_.

![kuva](https://github.com/KohaSuomi/kohasuomi.github.io/assets/33121325/b32231fa-d72d-4208-95b4-fa3fbd3abd2b)


Lisäksi cron-ajoon pitää laittaa "vipu" _prefer email_. Tämän tekee kehittäjät.

## RDA ja poikkeava pääsana

Jos on tarve poiketa kuvailusääntöjen mukaisista pääsanoista, voi käyttää 942him-kenttiä ohittamaan normaalikäytännöt. Alla linkki ohjeeseen.

[RDA ja poikkeava pääsana](/dokumentaatio/rdanuotti/)
