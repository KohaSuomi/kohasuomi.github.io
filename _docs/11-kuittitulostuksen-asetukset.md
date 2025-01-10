---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/kuittitulostuksen-asetukset/
redirect_from:
  - /theme-setup/
toc: true
---

# 11. Kuittitulostuksen asetukset

Koha-Suomi tukee Firefoxin ESR-versiota.

Tällä sivulla on ensin "yleisohje" uudemmille selaimille ja sen jälkeen erityishuomioita ja ohjeita liittyen tiettyihin selainversioihin. Näiden jälkeen ohjeistetaan, miten selain saadaan tulostamaan kuitit ilman, että pitää valita hiirellä OK (tai painaa enteriä). Lopuksi vielä ohjeita liittyen selaimen päivittymiseen ja ponnahdusikkoihin.

## 11.1 Firefox ESR

Avaa selaimen Valikko-menu ja valitse "Tulosta...".

![](/assets/files/docs/Kuittitulostuksen_asetukset/valikko.PNG)

Avautuvan sivun tulostinasetukset:
- Kohde: valitse alaspudotusvalikosta käyttämäsi kuittitulostin (Epson, Citizen jne).
- Kopioita: 1
- Suunta: Pysty
- Sivut: Kaikki
- Väritila: Mustavalkoinen

![](/assets/files/docs/Kuittitulostuksen_asetukset/Tulosta_asetukset1.PNG)

Klikkaa tämän jälkeen "Enemmän asetuksia".
- Paperin koko: valitse sopiva vaihtoehto. Yleisin koko on 80x297 mm.
- Koko: Sovita sivun leveyteen
- Sivuja per arkki: 1
- Reunukset: Ei reunuksia
- Ota pois valinnat: "Tulosta ylä- ja alatunnisteet" ja "Tulosta taustat".

![](/assets/files/docs/Kuittitulostuksen_asetukset/Tulosta_asetukset2.PNG)

Kun asetukset ovat kunnossa, tulosta kuittitulostimella yksi testitulostus. 
Riippuen millä sivulla olet, tämä kuitti voi vielä näyttää oudolta. 
Testitulostuksen jälkeen, määritä selain tulostamaan automaattisesti kohdan 9.2 mukaisesti.

## 11.1.1 Firefoxin versio 115+esr

- Tulostimen ajureista riippuen, tulostinasetuksiin kohtaan **Reunukset** valitaan "Oma (mm)" tai "Mukautettu (tuumina)".
  - Jos arvot annetaan tuumina: Reunukset laitetaan muuten nollaksi, mutta vasemman reunan arvoksi laitetaan 0,05.
  - Jos arvot annetaan millimetreinä: Reunukset laitetaan muuten nollaksi, mutta vasemman reunan arvoksi laitetaan 1,2.
- Kuittitulostimissa voi olla hieman eroja, joten jos annetut arvot eivät riitä, voi kokeilla hiukan suurentaa tai pienentää lukuja.

  ![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostinasetukset.PNG)

## 11.1.2 Firefoxin versiot 90+esr ja 100+esr

Huom! Firefoxin 90+ -versioissa kuittitulostukset eivät välttämättä toimi tai ne toimivat vain sen istunnon ajan, kun tulostusasetukset ovat määritelty. 
100+ -selainversioita kirjastoilla on käytössä ja ne ovat toimineet ongelmitta.

## 11.1.3 Firefoxin versio 78+esr

Avaa selaimen valikko oikeasta yläkulmasta ja valitse sieltä Tulosta.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer1.png)

Mene sivun asetuksiin.  
**Muoto ja valinnat** -välilehdeltä valitse **“Sovita sivun leveyteen”**.

![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostin2.png)

**Marginaalit ja ylä-/alatunnisteet** -välilehdellä muuta kaikki marginaalit
0:ksi ja kaikkiin ylä- ja alatunnisteisiin valitse --tyhjä--. Tämä asetus
käyttää kaiken tilan kuitin tulostukseen.

![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostin3.png)

Klikkaa lopuksi _OK_.

### 11.1.3.1 Oletustulostimen määrittely

Aseta oletustulostin Firefoxiin, niin et joudu joka kerta erikseen valitsemaan
tulostinta Tulosta-valikosta.

Mene vasemmasta yläkulmasta **Tulosta**-valikkoon.

Valitse valikosta käytössä oleva kuittitulostimesi ja klikkaa
_Ominaisuudet_ tai _Määritykset_ -painiketta, riippuen tulostusikkunan
ulkonäöstä.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer3.png)

Käy tarkistamassa **Asettelu**-välilehdeltä, että Paperikoko- ja
Tulostuspaperi -asetukset ovat oikein. Kuitin koko voi olla esimerkiksi 80 x 297 mm, 
72 x kuitti tms. Toiminnot riippuvat kuittitulostimen valinnoista.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer2.png)

Tallenna asetukset valitsemalla _OK_.

Tulosta lopuksi ensimmäinen sivu valitulle tulostimelle painamalla _OK_.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer4.png)


## 11.2 Selaimen määrittely tulostamaan kuitit automaattisesti

VAROITUS

Näin määritetty print.always_print_silent -asetus estää tulostimen vaihtamisen Firefoxissa eli jos haluat tulostaa muuta kuin kuitteja Kohasta (tai muilta sivuilta), käytä kaiken muun tulostamiseen toista selainohjelmaa.

Mene Firefoxiin. Kirjoita Firefoxin osoiteriville _about:config_. Saat varoituksen, että lisäasetusten muuttaminen voi vaikuttaa Firefoxin suorituskykyyn ja tietoturvaan, klikkaa _“Hyväksy riski ja jatka”_.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer5.png)

Kirjoita hakukenttään print.always. Jos ominaisuus _print.always_print_silent_ löytyy, muuta sen arvoksi true (=kyllä) klikkaamalla kaksisuuntaisen nuolen kuvaa rivin oikeassa reunassa.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer6.png)

Jos _print.always_print_silent_ -ominaisuutta ei löydy, lisää tämä ominaisuus:

- kirjoita ominaisuuden nimi kokonaisuudessaan hakukenttään (esimerkkikuvassa se ei ole kokonaan, koska arvo oli jo olemassa)
- laita valinta kohtaan _Totuusarvo_ ja klikkaa hiirellä plussa-painiketta
- muuta arvo tarvittaessa true-tilaan.

![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostin8.png)



## 11.3 Selaimen päivittyessä

Jos Firefox-selain päivittyy, eikä kuittitulostus toimi, tarkista
kuittitulostuksen asetukset. Vaihda yllä kuvatun
_print.always_print_silent_-määrityksen asetus true -> false, niin pääset asetuksiin. Kun asetukset on muutettu toimiviksi, vaihda asetus takaisin asetus false -> true.


## 11.4 Ponnahdusikkunat

Jos kuitin tulostusvaiheessa tulee ilmoitus, ettei ponnahdusikkunat ole
sallittuja, käy lisäämässä selaimen Tietosuoja ja turvallisuus
-asetuksissa kohtaan “Estä ponnahdusikkunat” poikkeukset
kimppasi/kirjastosi Koha-sivustolle.  
![](/assets/files/docs/Kuittitulostuksen_asetukset/ponnahdusikkuna.PNG)

Esimmerkissä OUTI-kimpan poikkeus:

![](/assets/files/docs/Kuittitulostuksen_asetukset/sallitut_sivustot2.PNG)

