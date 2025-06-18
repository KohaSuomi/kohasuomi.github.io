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
