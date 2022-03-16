---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/kuittitulostuksen-asetukset/
redirect_from:
  - /theme-setup/
toc: true
---

# 9. Kuittitulostuksen asetukset

Koha-Suomi tukee Firefox ESR-versiota.

## 9.1. Firefoxin versio 78+

Avaa selaimen valikko oikeasta yläkulmasta ja valitse sieltä Tulosta.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer1.png)

Mene sivun asetuksiin.  
Muoto ja valinnat -välilehdeltä valitse “Sovita sivun leveyteen”.

![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostin2.png)

Marginaalit ja ylä-/alatunnisteet-välilehdellä muuta kaikki marginaalit
0:ksi ja kaikkiin ylä- ja alatunnisteisiin valitse --tyhjä--. Tämä asetus
käyttää kaiken tilan kuitin tulostukseen.

![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostin3.png)

Klikkaa lopuksi _OK_.

---

## 9.2 Oletustulostin Firefoxiin

Aseta oletustulostin Firefoxiin, niin et joudu joka kerta erikseen valitsemaan
tulostinta Tulosta-valikosta.

Mene vasemmasta yläkulmasta Tulosta-valikkoon.

Valitse valikosta käytössä oleva kuittitulostimesi ja klikkaa
_Ominaisuudet_ tai _Määritykset_ -painiketta, riippuen tulostusikkunan
ulkonäöstä.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer3.png)

Käy tarkistamassa Asettelu-välilehdeltä, että Paperikoko ja
Tulostuspaperi -asetukset ovat oikein. Toiminnot riippuvat
kuittitulostimen valinnoista.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer2.png)

Tallenna asetukset valitsemalla _OK_.

Tulosta lopuksi ensimmäinen sivu valitulle tulostimelle painamalla _OK_.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer4.png)

---

## 9.3 Selaimen määrittely tulostamaan automaattisesti

Mene Firefoxiin. Kirjoita Firefoxin osoiteriville _about:config_. Saat
varoituksen vaarallisesta sivusta, klikkaa _“Otan riskin!”_.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer5.png)

Kirjoita hakukenttään print.always. Jos ominaisuus
_print.always_print_silent_ löytyy, muuta sen arvoksi true (=kyllä)
klikkaamalla hiiren oikealla painikkeella arvoa false. Valitse valikosta
Vaihda tila.

![](/assets/files/docs/Kuittitulostuksen_asetukset/printer6.png)

Jos _print.always_print_silent_ -ominaisuutta ei löydy (useimmissa selaimissa sitä ei ole
valmiina), lisää tämä ominaisuus:

- klikkaa hiiren oikeaa painiketta ominaisuusalueella ja valitse Uusi
  -&gt; Totuusarvo.

![](/assets/files/docs/Kuittitulostuksen_asetukset/tulostin8.png)

- kirjoita avautuvaan kenttään _print.always_print_silent_ ja
  klikkaa OK. Valitse totuusarvoksi _true_. Tämä muuttaa Firefoxin
  asetuksia siten, että se käyttää aina samoja asetuksia tulostuksessa
  eikä näytä kyselyä tulostamisesta.

VAROITUS  
Näin määritetty print.always_print_silent -asetus estää tulostimen
vaihtamisen Firefoxissa eli jos haluat tulostaa muuta kuin kuitteja,
käytä tulostamiseen toista selaiohjelmaa.

### 9.3.1 Selaimen päivittyessä

Jos Firefox-selain päivittyy, eikä kuittitulostus toimi oikein, tarkista
kuittitulostuksen asetukset. Joskus joutuu myös poistamaan yllä kuvatun
_print.always_print_silent_-määrityksen ja tekemään sen uudelleen.

---

## 9.4 Ponnahdusikkunat

Jos kuitin tulostusvaiheessa tulee ilmoitus, ettei ponnahdusikkunat ole
sallittuja, käy lisäämässä selaimen Tietosuoja ja turvallisuus
-asetuksissa kohtaan “Estä ponnahdusikkunat” poikkeus
kimppasi/kirjastosi Koha-sivustolle.  
![](/assets/files/docs/Kuittitulostuksen_asetukset/ponnahdusikkuna.png)

Esimmerkissä OUTI-kimpan poikkeus:

![](/assets/files/docs/Kuittitulostuksen_asetukset/sallitut_sivustot2.PNG)

## 9.1.2 Firefoxin versio 90+

Firefoxin 90+ -versioissa kuittitulostukset eivät välttämättä toimi tai ne toimivat vain sen istunnon ajan, kun tulostusasetukset ovat määritelty. Jos Kohaa käytetään Firefoxin uusimilla selainversioilla, alla esimerkkiasetukset, joilla tulostus voidaan saada toimimaan ainakin osittain.

Avaa selaimen Valikko-menu ja valitse "Tulosta...".

![](/assets/files/docs/Kuittitulostuksen_asetukset/valikko.PNG)

Avautuvan sivun asetukset:
- Kohde: valitse alaspudotusvalikosta käyttämäsi kuittitulostin.
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
- Ota pois valinnat: Tulosta ylä- ja alatunnisteet ja "Tulosta taustat.

![](/assets/files/docs/Kuittitulostuksen_asetukset/Tulosta_asetukset2.PNG)

Kun asetukset ovat kunnossa, tulosta kuittitulostimella yksi testitulostus. 
Riippuen millä sivulla olet, tämä kuitti voi vielä näyttää oudolta. 
Testitulostuksen jälkeen, määritä selain tulostamaan automaattisesti kohdan 9.3 mukaisesti.
