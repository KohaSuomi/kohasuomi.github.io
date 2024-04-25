---
title: 'Kohan ohje suomeksi'
permalink: /dokumentaatio/tyokalut/
redirect_from:
  - /theme-setup/
toc: true
---

# 12. Työkalut

_Työkalut_-osiossa on monenlaisia toimintoja, joilla voi esim. määritellä ilmoitusten ja kuittien tekstejä, käyttää siirtokokoelmia tai määritellä kalenteriin kirjaston kiinniolopäivät. Käyttäjän oikeuksista riippuu, mitä työkaluja hänelle on näkyvissä.

Osa työkaluista ei ole käyttökelpoisia tai tarpeellisia Koha-Suomen toimintaympäristössä. Nämä työkalut on merkitty kuvaan punaisella rastilla.

Koha-Suomen omiin tarpeisiin kehitetyt työkalut (varausten noutoilmoitusten ja myöhästymisilmoitusten tulostus, sotuteekki, tarratulostus)
löytyvät _Työkaluliitännäiset_-otsikon alta.

<img src="/assets/files/docs/Tyokalut/tyokalut.png" title="Kuvakaappaus Työkalut-osion aloitussivusta. Työkalun nimen perässä on punainen rasti, jos se ei ole käyttökelpoinen Koha-Suomessa." alt="Kuvakaappaus Työkalut-osion aloitussivusta. Työkalun nimen perässä on punainen rasti, jos se ei ole käyttökelpoinen Koha-Suomessa." style="width:90.0%" />

Osa aiemmin _Työkalut_-osiossa sijainneista toiminnoista, esim. niteiden ja tietuiden poisto tai muokkaus eräajona, on siirretty tässä versiossa (22.11) _Kuvailu_-osioon.
  
---

## 12.1 Asiakaslistat

**Huom!** _Asiakaslistat_-ohjetta ei ole päivitetty versioon 22.11, koska asiakashaku ei toimi oikein. Korjaus on tulossa versioon 23.05. Lisää siihen asti asiakkaita listalle tavallisen asiakashaun kautta.
{: .notice--warning}

_Asiakaslistat_-työkalulla voi luoda asiakkaista listoja, joita voi sitten
hyödyntää mm. asiakastietojen erämuokkauksessa (kts. 12.5).

Etusivulla listataan olemassa olevat asiakaslistat. Uuden asiakaslistan
voi tehdä _Uusi asiakaslista_ -painikkeesta.

<img src="/assets/files/docs/Tyokalut/asiakaslistat00.png" alt="Kuvakaappaus uuden asiakaslistan luomisesta" style="width:90.0%" />

Anna listalle nimi ja tallenna se. Jos lista merkitään jaetuksi, sen näkevät kimpassa kaikki, joilla on oikeus muokata asiakaslistoja.

<img src="/assets/files/docs/Tyokalut/asiakaslistat01.png" alt="Kuvakaappaus uuden asiakaslistan nimeämisestä ja jaetuksi merkitsemisestä" 
style="width:60.0%" />

Tämän jälkeen listalle voi lisätä asiakkaita klikkaamalla
_Toiminnot_-painiketta ja valitsemalla _Lisää asiakkaita_, kuten kuvassa. Toinen tapa on klikata lista lista auki sen nimestä.

<img src="/assets/files/docs/Tyokalut/asiakaslistat02.png" alt="Kuvakaappaus asiakkaiden lisäämisestä uuteen asiakaslistaan" style="width:90.0%" />

Siitä aukeaa sivu, jolla pystyt hakemaan asiakkaita esim. nimellä.
Valitse hiirellä tarjottu asiakastieto, jolloin se listautuu hakukentän
alapuolelle. Voit hakea useamman asiakkaan tiedot ennen kuin lisäät
heidät listalle.  
<img src="/assets/files/docs/Tyokalut/asiakaslistat03.png" alt="Kuvakaappaus asiakkaiden hakemisesta tietokannasta asiakaslistaan lisäämistä varten" 
style="width:90.0%" />

<img src="/assets/files/docs/Tyokalut/asiakaslistat04.png" alt="Kuvakaappaus useammasta haetusta asiakkaasta valmiina lisättäväksi asiakaslistaan" 
style="width:90.0%" />

Nyt pääset tarkastelemaan listalla olevia asiakkaita. Voit myös poistaa
heitä listalta valitsemalla heidän tiedot ja klikkaamalla _Poista
valitut asiakkaat_. Ohjelma kysyy varmistuksen “Haluatko varmasti poistaa valitut asiakkaat?”.
Huom! Asiakastietoja ei poisteta rekisteristä, vain asiakaslistalta.  
<img src="/assets/files/docs/Tyokalut/asiakaslistat05.png" alt="Kuvakaappaus esimerkkiasiakaslistaan kuuluvista asiakkaista" style="width:90.0%" />

Asiakkaita voi lisätä listalle myös tavallisen asiakashaun kautta valitsemalla
ensin halutut asiakkaat ja valitsemalla sitten _Lisää asiakaslistaan_
-valikosta haluamasi lista.  
<img src="/assets/files/docs/Tyokalut/asiakaslistat06.png" alt="Kuvakaappaus asiakkaiden lisäämisestä asiakaslistaan vaihtoehtoisella tavalla, normaalin 
asiakashaun kautta" style="width:90.0%" />

---

## 12.2 Ilmoitukset ja kuitit

Ilmoituksia ja kuitteja ylläpitävät pääsääntöisesti kimppojen
pääkäyttäjät, mutta tässä voi olla kimppakohtaisia eroja.

Ilmoitukset ja kuitit -työkalun etusivulla on lista olemassa olevista
pohjista. Ilmoitukset voivat olla joko kaikkia kirjastoja koskevia (oletuksena) tai
kirjastokohtaisia. Kaikki ilmoitus- ja kuittipohjat eivät välttämättä ole käytössä omassa kimpassasi.

<img src="/assets/files/docs/Tyokalut/ilmoitukset00.png" alt="Kuvakaappaus Ilmoitukset ja kuitit -osion etusivusta, jossa listataan käytössä olevat ilmoitus- ja kuittipohjat" style="width:90.0%" />

- Uusi pohjia voi tehdä _Uusi ilmoitus_ -napilla
- Pohjan voi kopioida toiselle kirjastolle _Kopioi_-napilla
- Pohjaa voi muokata _Muokkaa_-napilla
- Pohjan voi poistaa _Poista_-napilla. Kaikissa pohjissa poistomahdollisuutta ei ole, tällä halutaan estää mahdollisten virhetilanteiden synty järjestelmässä.

### 12.2.1 Ilmoituksen muokkaaminen

Ilmoituksen tai kuitin voi tehdä samoille kielille kuin mitä Kohaan on
asennettu käyttökieliksi (suomi, englanti, ruotsi). Lisäksi on olemassa _Oletus_-pohja, jota
käytetään silloin, kun asiakkaalle ei ole asiakastiedoissa valittuna asiointikieltä. Koha-Suomessa on kuitenkin käytössä pakotus, joka asettaa asiointikieleksi suomen, jos muuta (englanti, ruotsi) ei ole valittu. Tämä estää joissain tapauksissa sekakieliset ilmoitukset _Oletus_-pohjasta.

Ilmoituksen voi määrittää eri viestityypeille: sähköposti, tuloste, tekstiviesti jne.
Osa kuiteista, erityisesti lainaus-, varaus- ja kuljetuskuitit vaativat toimiakseen tekstin myös sähköpostikenttään, vaikka vain tuloste olisi käytössä. 
Muutokset tallennetaan _Tallenna_-napista. 

<img src="/assets/files/docs/Tyokalut/ilmoitukset01.png" alt="Kuvakaappaus ilmoitusten ja kuittien muokkauksen pääsivusta, jossa näkyvät käytössä olevat kielet ja viestityypit" style="width:90.0%" />

Ilmoitukseen tai kuittiin voi lisätä tekstiä sekä tägejä, joilla viestiin
lisätään tietokannasta tietoja esim. asiakkaasta, lainoista ja eräpäivistä. 
Tägejä voi lisätä vasemman reunan valikosta tai kirjoittaa ne itse.

_Viestin aihe_ -kenttään kirjoitetaan sähköpostiviestin aihe, joka näkyy myös asiakkaalle. Siihen kannattaa siis kiinnittää erityistä huomiota.
Myös viestin aiheessa voi käyttää tietokanta-tägejä. Jos viesti on html-muotoinen, laitetaan rasti kohtaan
_HTML-viesti_, jolloin viesti osataan käsitellä oikein. 

<img src="/assets/files/docs/Tyokalut/ilmoitukset02.png" alt="Kuvakaappaus, jossa esimerkkinä sähköposti-ilmoituksesta on eräpäivämuistutus" style="width:90.0%" />

Lisätietoja ja -ohjeita ilmoitusten muokkaamisesta on englanninkielisessä [Koha-wikissä](https://wiki.koha-community.org/wiki/Customising_Notices_and_Slips)

### 12.2.2 Eräpäivä kuitille ilman kellonaikaa

Eräpäivän saa tulostumaan kuitille ilman kellonaikaa dateonly-määreellä
näin:

Eräpäivä: &lt;&lt;issues.date_due \| dateonly &gt;&gt;

---

## 12.3 Myöhästymisilmoitusten määrittely

Myöhästymisilmoitusten eli palautuskehotusten aikataulu määritetään
_Myöhästymisilmoitusten määrittely_ -työkalulla. Määrittelyt voivat olla
joko kaikkia (_Oletus_) tai yksittäisiä kirjastoja koskevia. Ilmoituksia voi
lähettää kolme, mutta kaikkia tai mitään ei tarvitse lähettää. Jos kimpassa on käytössä _Laskutustyökalu_-liitännäinen, esim. kolmas ilmoitus saattaa viitata laskuun.

Huomioi, että jos oletussääntö on määritetty, ei yksittäiselle
kirjastolle pysty tekemään sääntöä, että ilmoituksia ei lähetetä
ollenkaan.

<img src="/assets/files/docs/Tyokalut/myohastymisilmoitukset.png" title="Kuvakaappaus taulukosta, jossa määritellään lähetettävät myöhästymisilmoitukset" alt="Kuvakaappaus taulukosta, jossa määritellään lähetettävät myöhästymisilmoitukset" style="width:90.0%" />

- Taulukossa listataan ne asiakastyypit, joille on määritetty
  asiakastyyppien ylläpidossa, että myöhästymisilmoituksia lähetetään.
- _Viive_-kenttään määritetään, montako päivää eräpäivän jälkeen
  myöhästyisilmoitus lähetetään. Järjestelmäasetuksella voidaan erikseen määritellä, otetaanko kirjaston kiinniolopäivät tässä huomioon.
- _Kirje_-sarakkeessa valitaan, mitä ilmoituspohjaa käytetään viestiä
  lähetettäessä. Ks. kohta 12.2 Ilmoitukset ja kuitit.
- _Rajoita_-kohtaan laitetaan rasti, jos halutaan asiakkaan menevän
  lainakieltoon viestin lähdettyä. Järjestelmäasetuksella voidaan erikseen määritellä, poistuuko rajoite automaattisesti lainojen palauduttua.
- _Maksu_-kohtaan määritetään ilmoituksesta perittävän maksun määrä. Maksuttoman ilmoituksen sarake jätetään tyhjäksi.
- _Sähköposti_, _Tuloste_, _Tekstiviesti_ jne -kohdista valitaan
  halutut vaihtoehdot kimpan viestien lähetystapojen mukaan.
- Määrittelyt tallennetaan _Tallenna muutokset_ -painikkeella.

---



## 12.4 Asiakkaiden poisto/lainatietojen poisto eräajona

Asiakkaita ja lainatietoja voi poistaa eräajona seuraavien ehtojen
mukaisesti:  

<img src="/assets/files/docs/Tyokalut/asiakkaidenpoisto1V2022.PNG" title="Kuvakaappaus asiakkaiden ja lainatietojen poisto eräajona -sivulta" alt="Kuvakaappaus asiakkaiden ja lainatietojen poisto eräajona -sivulta" style="width:90.0%" />

- ylimmäisenä, otsikon yläpuolella, on _Valitse kirjasto_ -vaihtoehto,
  eli voit määrittää koskeeko ajo kaikkia kirjastoja vai vain tiettyä
  kirjastoa
- jotka eivät ole lainanneet määritetyn päivämäärän jälkeen
- joiden tili on vanhentunut ennen määritettyä päivämäärää
- jotka eivät ole olleet yhteydessä (kirjautuneet verkkokirjastoon)
  määritetyn päivämäärän jälkeen
- joiden asiakastyyppi on alasvetovalikosta valitun mukainen
- jotka ovat asiakaslistalla, jonka voi valita alasvetovalikosta

Kaikkia vaihtoehtoja voi yhdistellä keskenään asiakastietoja
poistettaessa.

### 12.4.1 Asiakkaiden poisto

Valitse haluamasi vaihtoehto/vaihtoehdot ja laita rasti
_Vahvista: Haluat varmasti poistaa asiakkaita_-ruutuun. Klikkaa sitten _Seuraava_-nappulaa.

Seuraavaksi kerrotaan, kuinka monta asiakasta ollaan poistamassa ja mitä niille halutaan tehdä.  

<img src="/assets/files/docs/Tyokalut/asiakkaidenpoisto2V2022.PNG" title="Kuvakaappaus, jossa kerrotaan kuinka monta asiakasta ollaan poistamassa ja kysytään, mitä asiakastiedoille halutaan tehdä" alt="Kuvakaappaus, jossa kerrotaan kuinka monta asiakasta ollaan poistamassa ja kysytään, mitä asiakastiedoille halutaan tehdä" style="width:90.0%" />

- Poistetaanko näiden asiakkaiden tiedot pysyvästi
  - **Huom!** Tämä vaihtoehto poistaa asiakastiedot täysin järjestelmästä, eikä niitä viedä deletedborrower-tauluun. Käytä vain, jos haluat poistaa asiakastiedot täysin järjestelmästä ja tilastoista.
- Siirrä näiden asiakkaiden tiedot roskakoriin
  - tämä vaihtoehto siirtää asiakastiedot deletedborrowers-tauluun. Tätä vaihtoehtoa kannattaa käyttää pääsääntöisesti.
- Älä poista asiakastietoja (testiajo)

Valitse haluamasi vaihtoehto ja klikkaa _Valmis_-nappulaa.

Tämän jälkeen järjestelmä kertoo, kuinka monta asiakasta poistettiin, siirrettiin roskakoriin (deletedborrowers-tauluun) tai montako asiakastietoa olisi siirretty roskakoriin ja anonymisoitu, jos kyseessä ei olisi ollut testiajo. 

<img src="/assets/files/docs/Tyokalut/asiakkaidenpoisto2.png" title="Kuvakaappaus, jossa kerrotaan kuinka monta asiakasta on siirretty roskakoriin" alt="Kuvakaappaus, jossa kerrotaan kuinka monta asiakasta on siirretty roskakoriin" style="width:90.0%" />

### 12.4.2 Lainahistorian anonymisointi

Poista asiakkaita -toiminnon alapuolella on lainahistorian anonymisointi -toiminto. Ihan ylimmäisenä, ennen asiakkaiden poistoa ja otsikon yläpuolella on Valitse kirjasto -vaihtoehto, josta voit valita, koskeeko anonymisointi kaikkia kirjastoja vai vain tiettyä kirjastoa.

- Laita rasti kohtaan _Vahvista: Haluat anonymisoida asiakkaiden lainahistorian_.
- Valitse päivämäärä, mitä vanhemmat asiakkaiden lainahistoriat poistetaan.
- Klikkaa _Seuraava_

Saat tiedon, kuinka monen asiakkaan lainahistoria anonymisoidaan.

<img src="/assets/files/docs/Tyokalut/asiakkaidenanonymisointi1V2022.PNG" title="Kuvakaappaus, jossa varoitetaan, kuinka monen asiakkaan lainahistoria anonymisoidaan" alt="Kuvakaappaus, jossa varoitetaan, kuinka monen asiakkaan lainahistoria anonymisoidaan" style="width:90.0%" />

- Valitse _Valmis_

<img src="/assets/files/docs/Tyokalut/asiakkaidenanonymisointi2V2022.PNG" title="Kuvakaappaus, jossa kerrotaan, kuinka monta lainaa on anonymisoitu, jotka ovat valittua päivämäärää vanhempia" alt="Kuvakaappaus, jossa kerrotaan, kuinka monta lainaa on anonymisoitu, jotka ovat valittua päivämäärää vanhempia" style="width:90.0%" />

---

## 12.5 Asiakkaiden muokkaus eräajona

Asiakkaiden tietoja voi muokata eräajona eli tehdä sama muutos isommalle joukolle kerralla.

<img src="/assets/files/docs/Tyokalut/asiakkaidenmuokkaus_v2023_1.jpg" title="Kuvakaappaus asiakkaiden muokkaus eräajona sivun näkymästä" alt="Kuvakaappaus asiakkaiden muokkaus eräajona sivun näkymästä" style="width:90.0%" />  

Muokattavat asiakkaat voi valita kolmella tavalla
- tiedostosta
- asiakaslistalta
- lisäämällä heidän kirjastokortin numeron tekstikenttään, yksi per rivi

Sen jälkeen valitaan _Seuraava_

<img src="/assets/files/docs/Tyokalut/asiakkaidenmuokkaus2V2022.PNG" title="Kuvakaappaus valittavista kentistä asiakkaiden muokkausnäkymästä" alt="Kuvakaappaus valittavista kentistä asiakkaiden muokkausnäkymästä" style="width:90.0%" />

Asiakkaille voi joko lisätä tai poistaa tietoja. Poistaminen tapahtuu laittamalla rasti kentän viereen. Huomioi, että poisto tehdään kaikille eräajossa muutettavaksi valitsemillesi asiakkaille. Lopuksi valitaan _Tallenna_.

---

## 12.6 Kalenteri

Kalenteri-työkalulla voi määrittää kirjaston aukiolo- ja sulkupäivät. Jos päivä on merkitty kalenterissa suljetuksi, ei sille tule eräpäiviä eikä varausten viimeisiä noutopäiviä. Kalenterit määritetään erikseen jokaiselle kirjastolle.

Kun sivulle menee, avautuu näkyville käyttäjän kirjautumiskirjaston kalenteri. Sen oikealle puolelle avautuu Vinkit-ruutu, jossa on selitykset sulkuvaihtoehdoiksi sekä listoja jo määritetyistä
kiinniolopäivistä.

<img src="/assets/files/docs/Tyokalut/Pekurinkirjastonkalenteri.png" title="Kuvakaappaus kalenteri-työkalun näkymästä. Kalenterinäkymässä on Oulun kaupungin Pekurin kirjaston kalenteri huhtikuulta 2024." alt="Kuvakaappaus kalenteri-työkalun näkymästä. Kalenterinäkymässä on Oulun kaupungin Pekurin kirjaston kalenteri huhtikuulta 2024." style="width:90.0%" />

<img src="/assets/files/docs/Tyokalut/Kalenterivinkit.png" title="Kuvakaappaus kalenteri-työkalun Vinkit-ruudusta, jossa on selitykset sulkuvaihtoehdoiksi sekä listoja jo määritetyistä
kiinniolopäivistä." alt="Kuvakaappaus kalenteri-työkalun Vinkit-ruudusta, jossa on selitykset sulkuvaihtoehdoiksi sekä listoja jo määritetyistä
kiinniolopäivistä." style="width:90.0%" />

### 12.6.1 Kiinniolon lisääminen

Lisää kiinniolopäivä-valikko avautuu klikkaamalla kalenterista haluttua päivämäärää tai
päivämäärävälin ensimmäistä päivää. 

<img src="/assets/files/docs/Tyokalut/Lisaakiinniolopaiva.png" title="Kuvakaappaus, jossa näkyy valittavissa olevat vaihtoehdot infoteksteineen. Tarkempi kuvaus varsinaisessa tekstissä" alt="Kuvakaappaus, jossa näkyy valittavissa olevat vaihtoehdot infoteksteineen. Tarkempi kuvaus varsinaisessa tekstissä" style="width:90.0%" />

Päivään -kenttään voi lisätä kiinnioloajan päättymispäivän, jos kiinniolopäivät lisätään aikavälille. Kiinniolopäivän ollessa yksittäinen, jätetään Päivään -kenttä tyhjäksi. Punaisesta ruksista Päivään -kentän saa tarvittaessa tyhjennettyä. Nimeke-kenttään voi kirjoittaa haluamansa nimen kiinniolopäivälle/aikavälille, esim. Suljettu tai Pääsiäinen.
Kuvaus-kenttään voi kuvata tarkemmin sulkutietoa. Sitten valitse yksi kiinniolovaihtoehdoista (kysymysmerkistä vaihtoehdon perässä saat tarkemman kuvauksen vaihtoehdosta. Yllä olevassa kuvassa on tarkemmat kuvaukset avattuina.):

- Kiinni vain tänä päivänä
  - yksittäinen kiinniolopäivä
- Kiinni joka viikko tänä päivänä
  - tällä voi määrittää helposti esim. kaikki sunnuntait kiinnioleviksi
- Kiinni joka vuosi samana päivänä
  - tällä voi määrittää joka vuosi samana kalenteripäivänä toistuvat juhlapyhät kiinnioleviksi, esim. jouluaatto
- Kiinni aikavälillä
  - tämä pitää valita, jotta Päivästä-päivään valinta ylempänä toimii
- Kiinni aikavälillä joka vuosi
  - toimii kuten Kiinni joka vuosi samana päivänä -vaihtoehto, mutta määritetäänkin aikaväli, esim. joulunpyhät
- Kopioi kaikkiin kirjastoihin
  - jos tähän laittaa rastin, kopioidaan määritys kaikkiin kimpan kirjastoihin. Kätevä toiminto silloin, kun pitää saada tehtyä järjestelmänlaajuisia määrityksiä. Esim. kaikki kirjastot on suljettu järjestelmäpäivityksen vuoksi tai kaikkia kirjastoja koskeva juhlapyhä.

Kopioi kiinniolopäivät kirjastolle -alasvetovalikosta voit valita kirjaston, jonka kalenteriin haluat kiinniolon kopioituvan.

<img src="/assets/files/docs/Tyokalut/Kalenteri3.png" title="Kuvakaappaus Kopioi kiinniolopäivät kirjastolle -valikosta" alt="Kuvakaappaus Kopioi kiinniolopäivät kirjastolle -valikosta" style="width:90.0%" />

Kalenterin alalaidassa olevista linkeistä pääset takaisin kuluvan kuukauden kohdalle, jos teet määrityksiä jonkin muun kuukauden kohdalla.

<img src="/assets/files/docs/Tyokalut/Kalenteri4.png" title="Kuvakaappaus kalenterissa olevista Eilinen, Today ja Huominen -linkeistä" alt="Kuvakaappaus kalenterissa olevista Eilinen, Today ja Huominen -linkeistä" style="width:90.0%" />

### 12.6.2 Sulkupäivien värikoodit

Eri tyyppiset sulkupäivät on merkitty eri väreillä.

<img src="/assets/files/docs/Tyokalut/Kalenteri5.png" title="Kuvakaappaus kalenterissa käytettyjen värien selitteestä" alt="Kuvakaappaus kalenterissa käytettyjen värien selitteestä" style="width:90.0%" />

- valkoinen on työpäivä eli päivälle voi tulla erä- ja noutopäiviä.
- punainen on yksittäinen, ei toistuva kiinniolopäivä. Myös
  aikavälillä suljetuksi merkityt päivät merkitään punaisella.
- keltainen on viikottain toistuva kiinniolopäivä. Myös
  aikavälillä suljetuksi merkityt päivät merkitään keltaisella.
- oranssi on vuosittain toistuva kiinniolopäivä.Myös
  aikavälillä suljetuksi merkityt päivät merkitään oranssilla.
- sininen on poikkeus määritettyyn kiinnioloon eli käytännössä päivä
  on avoin ja sille voi tulla erä- ja noutopäiviä.

Alla kuvakaappaus, miltä värikoodit näyttävät kalenterissa.

<img src="/assets/files/docs/Tyokalut/Kalenteri6.png" title="Kuvakaappaus kalenterista, jossa on punaisia, sininen, keltaisia ja oranssi merkintä" alt="Kuvakaappaus kalenterista, jossa on punaisia, sininen, keltaisia ja oranssi merkintä" style="width:90.0%" />

Kalenterissa klikattu päivä näkyy vihreänä. 

Kuluva päivä on näkyy tummanvihreällä kehystettynä, jos kyseinen päivä on avoinna oleva päivä. Jos päivä on merkitty suljetuksi,
näkyy siinä sulkupäivän tyypin mukainen väri vihreällä kehystettynä.

<img src="/assets/files/docs/Tyokalut/Kalenteri7.png" title="Kuvakaappaus kalenterista, jossa on ympyröity punaisella laatikolla kuluva päivä" alt="Kuvakaappaus kalenterista, jossa on ympyröity punaisella laatikolla kuluva päivä" style="width:90.0%" />

### 12.6.3 Sulkutiedon poistaminen ja muokkaaminen

Sulkupäiviä voi poistaa tai muokata, jos ne ovat virheellisiä tai tarpeettomia.

Valitse päivä tai aikavälin ensimmäinen päivä.

<img src="/assets/files/docs/Tyokalut/Muokkaakiinniolopaivaa.png" title="Kuvakaappaus, jossa on kiinniolopäivän poisto- ja muokkausvaihtoehdot: poista tämä päivä, poista yksittäiset kiinniolot aikavälillä, poista toistuvat kiinniolot aikavälillä, poista poikkeukset aikaväliltä, muokkaa kiinniolopäivää sekä Kopioi muutokset kaikkiin kirjastoihin" alt="Kuvakaappaus, jossa on kiinniolopäivän poisto- ja muokkausvaihtoehdot: poista tämä päivä, poista yksittäiset kiinniolot aikavälillä, poista toistuvat kiinniolot aikavälillä, poista poikkeukset aikaväliltä, muokkaa kiinniolopäivää sekä kopioi muutokset kaikkiin kirjastoihin" style="width:90.0%" />

Poistaessasi kiinnioloa voit määrittää tarvittaessa aikavälin loppupäivän. Valitse haluamasi poisto -vaihtoehto. Tallenna valinnat.

Muokatessasi kiinniolopäivää voit tehdä muutoksen vain yksi päivä kerrallaan. Valitse muutettava päivä ja muokkaa valitun päivän nimekettä ja kuvausta. Valitse
sitten vaihtoehto _Muokkaa kiinniolopäivää_ ja klikkaa Tallenna-nappia.

Voit kopioida valitsemasi poiston tai muokkauksen kaikkiin kimpan kirjastoihin valitsemalla vaihtoehdon _Kopioi muutokset kaikkiin kirjastoihin_ -vaihtoehdon. 

<img src="/assets/files/docs/Tyokalut/Kalenteri9.png" title="Kuvakaappaus, jossa näkyy muokkaustila ja on ympyröitynä punaisella laatikolla kohdat Nimeke, Kuvaus ja Muokkaa kiinniolopäivää" alt="Kuvakaappaus, jossa näkyy muokkaustila ja on ympyröitynä punaisella laatikolla kohdat Nimeke, Kuvaus ja Muokkaa kiinniolopäivää" style="width:90.0%" />

---

## 12.7 Lokien katselu

Lokien katselu -työkalulla pystyy hakemaan mm. asiakkaisiin, lainoihin,
maksuihin, varauksiin ja luettelointitietueisiin liittyviä muutoksia.
Työkaluun pääsee myös esim. asiakastietojen ja perustiedot-näytön
kautta, jolloin sinne on valmiiksi täytettynä asiakkan tai tietueen
tunnista. Järjestelmäasetuksissa Lokit-osiossa määritetään, mitä tietoja
tallennetaan muutoshistoriaan eli lokitetaan. Tiedot haetaan tietokannan
action_logs-taulusta.

Työkalun käyttö vaatii harjoittelua, jotta osaa tulkita tuloksia. Eri
osioissa ja toiminnoissa kirjataan asiaoita eri tavalla, joten mitään
kaikenkattavaa ohjetta ei pysty tekemään.

<img src="/assets/files/docs/Tyokalut/selaa_lokeja.png" title="Kuvakaappaus Lokien katselu -sivulta. Ylhäältä alas: Virkailija, osiot, toiminnot, ID-tunnus, tiedot, käyttöliittymä, alkupvm, loppupvm, selaimen näytölle, tiedostoon, nimi" alt="Kuvakaappaus Lokien katselu -sivulta. Ylhäältä alas: Virkailija, osiot, toiminnot, ID-tunnus, tiedot, käyttöliittymä, alkupvm, loppupvm, selaimen näytölle, tiedostoon, nimi" style="width:95.0%" />

Vaihtoehtojen kuvaukset ja sulkeissa valintaa vastaava taulun sarake
action_logs-taulussa:

- **Virkailija** (user): tähän kohtaan voi määrittää, minkä
  käyttäjätunnuksen tekemiä muutoksia haetaan. Kenttään laitetaan
  käyttäjän borrowernumber.
- **Osiot** (module): määrittele, minkä Kohan osion tietoja haluat
  hakea. Huutomerkkikolmio kuvake kertoo, että kyseisen osion lokitus ei ole päällä. Silloin siihen ei tietenkään voi myöskään kohdistaa hakua
- **Toiminnot** (action): valitse minkälaisia toimintoja haluat hakea.
- **ID-tunnus** (object): tähän määritellään tutkittavan tiedon
  tunniste, mikä riippuu siitä, mitä ollaan tutkimassa: asiakkaan
  borrowernumber, tietueen biblionumber, niteen itemnumber, varauksen
  id
- **Tiedot** (info): Tämän kentän tieto riippuu haettavasta osiosta,
  koska siihen kirjataan tehty muutos. Kirjaustapa vaihtelee eri
  toiminnoissa. Hakuehtona voi käyttää esim. biblionumberia,
  borrowernumberia tai itemnumberia. Kenttää voi kirjoittaa myös ihan
  sanoja, joita arvelee kirjatun muutoksiin, kuten phone.
- **Käyttöliittymä** (interface): mitä kautta muutos on tehty.
- **Alkupvm ja Loppupvm** (timestamp): tähän voi ja kannattaa
  määrittää aikavälin, miltä tietoja hakee. Lokitietoja on paljon,
  joten aikaväli kannattaa määrittää mahdollisimman tarkasti. Lisäksi
  ei ole monestikaan tarkoituksenmukaista esim. tutkia asiakkaan
  täydellistä muutoshistoriaa, jolloin rajaaminen on tarpeen.

Tulostus-otsikon alla

- **Selaimen näytölle**: tulokset näytetään selaimesssa
- **Tiedostoon ja nimi**: tulokset voi viedä CSV-tiedostoksi ja
  nimi-kenttään voi määrittää tiedostolle nimen.

Esimerkki, jossa haettu asiakkaan muutoslokilta kaikki tiedot tietyllä
välillä:

<img src="/assets/files/docs/Tyokalut/lokit3.png" title="Kuvakaappaus lokin hakutuloksista. Taulukko, jossa sarakkeet pvm, virkailija, osio, toiminto, ID-tunnus, tiedot ja käyttöliittymä" alt="Kuvakaappaus lokin hakutuloksista. Taulukko, jossa sarakkeet pvm, virkailija, osio, toiminto, ID-tunnus, tiedot ja käyttöliittymä" style="width:90.0%" />

- Virkailija nro 0 tarkoittaa, että muutoksen on tehnyt jokin järjestelmän oma toiminto, ei virkailija.

**Huom.** Lokien katselun kautta löytyvät lokitiedot kuluvan vuoden + 1 edellisen vuoden ajalta. Vanhemmat lokitiedot tulee hakea erikseen raporteilla. Koha-Suomen [säilytysajat](https://koha-suomi.fi/dokumentaatio/tietojensailytysajat/#tapahtumalokit).
{: .notice--warning}

---

## 12.8 Uutiset

Uutiset-työkalulla voi kirjoittaa uutisia tai tiedotteita virkailijaliittymään, Kohan verkkokirjastoon ja kuiteille. Uutisia voi kirjoittaa niillä kielillä, mitä omaan Kohaan on asennettu.

Linkit _HTML muokkaukset_, *OPACUserJS* ja *OPACUserCSS* liittyvät Kohan omaan verkkokirjastoon, joka ei käytössä Koha-Suomen kirjastoissa.

<img src="/assets/files/docs/Tyokalut/uutiset.png" title="Kuvakaappaus Uutiset-työkalun aloitusnäkymästä, jossa on useampi uutinen näkyvissä" alt="Kuvakaappaus Uutiset-työkalun aloitusnäkymästä, jossa on useampi uutinen näkyvissä" style="width:95.0%" />

- **Paikka**: missä uutinen näytetään
- **Kirjasto**: mille kirjastoille (perustuu kirjautumiskirjastoon)
  uutinen näytetään
- **Numero**: monentena näytetään, jos on useampi uutinen
- **Julkaisuvuosi**: julkaisupäivä
- **Vanhentumispvm**: Vanhentumispäivä, jos sellainen on määritetty
- **Nimeke**: Uutisen otsikko
- **Tekijä**: Uutisen tekijä. Uutisten kirjoittajaksi merkitään sisään
  kirjautunut käyttäjä. _NewsAuthorDisplay_ -järjestelmäasetuksella
  voi määrittää, piilotetaanko tai näytetäänkö uutisen kirjoittajan
  nimi.
- **Uutiset**: Uutisten esikatselu
- **Toiminnot**: Muokkaa-napista voi muokata uutista ja Poista-napista
  voi poistaa uutisen

Uutiset näkyvät virkailijaliittymässä etusivun vasemmassa reunassa.

<img src="/assets/files/docs/Tyokalut/uutiset5.png" title="Etusivulta kuvakaappaus, jossa näkyy kaksi uutista ja vähän muita osia sivusta" alt="Etusivulta kuvakaappaus, jossa näkyy kaksi uutista ja vähän muita osia sivusta" style="width:90.0%" />

### 12.8.1 Uuden uutisen luominen

Valitse sivun yläreunasta _Luo uusi_.

<img src="/assets/files/docs/Tyokalut/lisaa_uutinen.png" title="Kuvakaappaus uuden uutisen lisäyssivusta" alt="Kuvakaappaus uuden uutisen lisäyssivusta" style="width:90.0%" />

Valitse ja täytä tarvittavat tiedot:

- **Näyttöpaikka**: näytetäänkö uutinen kaikkialla,
  virkailijatyökalussa, kuiteissa vai Kohan omassa verkkokirjastossa (ei käytössä Koha-Suomen kirjastoissa)
- **Kirjasto**: näytetäänkö uutinen kaikille kirjastoille vai vain yhdelle valitulle kirjastolle
- **Julkaisuaika**: voi joko jättää tyhjäksi, jolloin uutinen
  julkaistaan heti tai valita tietty julkaisupäivä.
- **Vanhentumispvm**: voi joko jättää tyhjäksi, jolloin uutinen ei
  vanhene tai valita tietty vanhentumispäivä, jolloin uutinen
  piilotetaan käyttäjiltä valittuna päivänä.
- **Näyttöjärjestys**: jos uutisia on useampi, tällä voi määrittää
  niiden keskinäinen järjestys
- **Kielivälilehdet**: Eri kieliset uutiset eri kielivälilehdille.
- **Nimeke**: Uutisen nimi tai otsikko.
- **Sisältö**: Tähän kirjoitetaan varsinainen uutinen. Käytettävissä
  on WYSIWYG-muotoilut (what you see is what you get).

Tallenna valitsemalla *Tallenna* tai peruuta valitsemalla *Peruuta*.

### 12.8.2 Uutisen poistaminen

Uutisen voi poistaa klikkaamalla halutun uutisen kohdalla *Poista*-nappia. Useamman uutiset voi poistaa valitsemalla uutinen vasemmalta ruksilla ja painamalla *Poista valitut*.

<img src="/assets/files/docs/Tyokalut/uutisen_poisto.png" title="Uutiset-sivulta kuvakaappaus, jossa on ympyröitynä punaisella laatikolla Poista-nappula" alt="Uutiset-sivulta kuvakaappaus, jossa on ympyröitynä punaisella laatikolla Poista-nappula" style="width:90.0%" />

**Huom!** Vanhentuneet uutiset poistuvat käyttäjien näkyviltä vanhentumispäivänä, mutta eivät poistu automaattisesti uutislistasta. Ne pitää halutessaan poistaa manuaalisesti.
{: .notice--warning}

---

## 12.9 Työkaluliitännäiset

Työkaluliitännäiset löytyvät Työkalut-sivun Muut työkalut-palstalta. Koha-Suomella tällä hetkellä neljä työkaluliitännäistä: laskutustyökalu, tulosta ilmoituksia, sotuteekki ja tarratulostustyökalu.

<img src="/assets/files/docs/Tyokalut/tyokaluliitannaiset.png" title="Työkaluliitännäiset-sivulta kuvakaappaus, jossa luetellaan käytössä olevat liitännäiset" alt="Työkaluliitännäiset-sivulta kuvakaappaus, jossa luetellaan käytössä olevat liitännäiset" style="width:60.0%" />

### 12.9.1 Laskutustyökalu

<img src="/assets/files/docs/Tyokalut/laskutus.png" title="Näkymä laskutustyökalusta: rajaustoiminnot ja yhden testiasiakkaan laskutettavat niteet" alt="Näkymä laskutustyökalusta: rajaustoiminnot ja yhden testiasiakkaan laskutettavat niteet" style="width:100.0%" />

**Laskutettavien hakeminen**  
Laskutettava aineisto haetaan aikaväliltä. Sivulle tultaessa aikaväli muodostuu automaattisesti myöhästymisilmoituksissa olevan viiveen ja työkalun asetuksissa olevan asetuksen mukaan. Aikaväliä voi muuttaa tarvittaessa.

Tuloksia voi suodattaa asiakasryhmän ja minimisumman mukaan. Minimisumma kannattaa säätää nollaan, jotta mukaan tulee myös ne asiakkaat, joiden laskutettavien niteiden kaikki korvaushinnat ovat nolla tai tyhjä.

Rajausten alapuolella olevilla sinisillä painikkeilla voi luoda laskut tai jäljennökset kaikille hakutuloksen asiakkaille yhdellä kertaa.

**Laskutettava aineisto**  
Laskutettava aineisto näkyy kunkin asiakkaan alla, tiedot saa auki asiakkaan tiedoissa olevasta nuolesta.

Laskutettavasta aineistoista voi vielä tässä vaiheessa muokata korvaushintaa tai jättää jonkun aineiston pois laskulta ottamalla ruksin pois niteen kohdalta. Aineisto, jolle ei ole määritelty korvaushintaa jätetään alustavasti pois laskulta. Jos hinnan lisää, aineisto laskutetaan. Jos hintatietoa muokkaa, tallennetaan uusi hinta myös niteen tietoihin.

**Laskun luominen**  
Kun on tarkistanut laskutettavan aineiston tiedot, voi siitä luoda laskun vihreästä napista. Kimpasta ja kirjastosta riippuen se on PDF-lasku, elasku tai Finvoice-sanoma. 

Laskun luonti lisää niteille asetuksissa määritellyn "Laskutettu"-tilan. Jos sivun lataa uudestaan niin juuri äsken laskutettu aineisto ei enää näy listassa. Sen saa näkyviin kun valitsee *Näytä laskutetut*. 
- PDF:n, elasku-viestin ja Finvoice-sanoman luontiin käytetään käyttäjän kirjautumiskirjaston viestipohjaa. Jos laskuttaa kerralla useamman kirjaston aineistoa, pitää kirjautua siihen kirjastoon, jolle on luotu ODUECLAIM- tai FINVOICE-pohjat. Yleensä tämä on kunnan pääkirjasto.

PDF-laskun luomisen jälkeen siirrytään esikatselu-näkymään, jossa näkee sivun asettelun. Painamalla *Tulosta* avautuu PDF-tiedosto.

*Jäljenne*-napilla saa tulostettua myös PDF-laskutusta käytettäessä etu- tai jälkikäteen jäljenteen eli laskukopion. Napin painaminen ei aiheuta laskutusmerkintöjä.

Lasku luodaan asiakkaan ilmoituksiin, jolloin siitä jää jälki järjestelmään. Finvoice-sanomat lähetetään eteenpäin ajastetusti, joten korjauksia voidaan tehdä ennen lähetystä.

**Laskutettavien palautus**  
Kun asiakkaan kaikki laskutetut niteet palautetaan, poistuu asiakkaalta rajoite. Huom. Rajoite ei poistu automaattisesti takaajalta vain taattavasta. Jos osaa laskutetuista niteistä ei palauteta, jää rajoite paikalleen. Niteille jää laskutettu-tila ja asiakkaan tietoihin tieto (viesti), että hänelle on lähettetty lasku. Nämä tiedot pitää poistaa manuaalisesti.

Laskutuksen asetusten ohje on [GitHubissa](https://github.com/KohaSuomi/koha-plugin-overdue-tool/wiki/Laskutusty%C3%B6kalun-k%C3%A4ytt%C3%B6%C3%B6notto%E2%80%90ohjeet).


### 12.9.2 Tulosta ilmoituksia

*Tulosta ilmoituksia* -toimintoa käytetään, kun käytössä ei ole e-kirjepalvelua. Sillä tulostetaan pdf-muotoisia varausten saapumisilmoituksia sekä muistutuskirjeitä (palautuskehotuksia). *Tulosta ilmoituksia* -toiminto ei ole käytössä kaikissa kirjastokimpoissa.

<img src="/assets/files/docs/Tyokalut/tulostailmoituksia2.png" title="Näkymä tulosta ilmoituksia -työkalusta: yksi tulostettava noutoilmoitus IIT_PK-kirjastoon" alt="Näkymä tulosta ilmoituksia -työkalusta: yksi tulostettava noutoilmoitus IIT_PK-kirjastoon" style="width:100.0%" />

*Noutoilmoitukset*-näkymässä on listattu lähettämistä odottavat varausten saapumisilmoitukset. *Tulosta*-napista siirrytään esikatseluun ja *Peruuta*-napista viesti poistuu näkymästä ja asiakastietojen Ilmoitukset-näkymässä ilmoituksen tilaksi tulee *epäonnistunut*. *Kirjastopiste* tarkoittaa asiakkaan kotikirjastoa. Ei siis välttämättä varauksen noutokirjastoa.

<img src="/assets/files/docs/Tyokalut/tulostailmoituksia_esikatselu.png" title="Näkymä noutoilmoituksen esikatselusta: Iitin kirjastoon on menossa kirja SQL-ohjelmointi asiakkaalle Esko Esimerkki. Ylhäällä Takaisin- ja Tulosta-painikkeet" alt="Näkymä noutoilmoituksen esikatselusta: Iitin kirjastoon on menossa kirja SQL-ohjelmointi asiakkaalle Esko Esimerkki. Ylhäällä Takaisin- ja Tulosta-painikkeet" style="width:60.0%" />

Esikatselun *Takaisin*-napilla siirrytään takaisin ilmoituslistaan. *Tulosta*-napista ohjelma luo pdf-tiedoston, jonka voi sitten tulostaa. Tällöin asiakkaan ilmoitukset-näkymässä tilaksi tulee *lähetetty*. 
HUOM. pdf-näkymässä ei kannata painaa *Peruuta*, koska tällöin ilmoitus häviää *Tulosta ilmoituksia* -toiminnosta ja asiakkaan tiedoissa tilana näkyy silti lähetetty. Asian voi korjata menemässä asiakkaan tietoihin ja painamalla *Lähetä uudelleen*, jolloin viesti ilmestyy uudelleen *Tulosta ilmoituksia* -työkaluun. Tosin ongelmana voi olla ettei tiedä kenelle asiakkaalle viesti oli lähdössä.

Muistutusten kanssa toimitaan aivan samoin kuin noutoilmoitusten kanssa.

<img src="/assets/files/docs/Tyokalut/tulostailmoituksia_tulostus.png" title="Näkymä noutoilmoituksen pdf-tulostuksesta: vasemmalla saapumisilmoituskirje ja oikealla pdf-tulostuksen valikoita ja painikkeita" alt="Näkymä noutoilmoituksen pdf-tulostuksesta: vasemmalla saapumisilmoituskirje ja oikealla pdf-tulostuksen valikoita ja painikkeita" style="width:100.0%" />


### 12.9.3 Sotuteekki

Sotuteekistä löytyvät asiakkaiden henkilötunnukset. Sitä käytetään asiakaslaskutuksessa, kun halutaan selvittää laskutettavan asiakkaan henkilötunnus asiakkaan sotu-avaimen avulla.
Sotuteekkiin kirjaudutaan erillisillä tunnuksilla. Tunnukset ovat vain laskuttajilla. Kimppojen pääkäyttäjät voivat luoda tunnuksia, jos laskuttajissa tapahtuu muutoksia.

<img src="/assets/files/docs/Tyokalut/sotuteekki.png" title="Sotuteekki-sivulta kuvakaappaus, jossa ovat kentät tunnus, salasana ja sotu-avain" alt="Sotuteekki-sivulta kuvakaappaus, jossa ovat kentät tunnus, salasana ja sotu-avain" style="width:70.0%" />

### 12.9.4 Tarratulostustyökalu

Aloita tarratulostus valitsemalla tarrapohja.

<img src="/assets/files/docs/Tyokalut/valitsepohja.png" title="Valitse pohja -valikko" alt="Valitse pohja -valikko" style="width:20.0%" />

Valitse tulostettavat tarrat vasemmalta *Valitse lista* -alasvetovalikosta tai syöttämällä viivakoodit oikealle *Lue viivakoodit* -laatikkoon.

<img src="/assets/files/docs/Tyokalut/tulostus.png" title="Näkymä tarratulostussivulta" alt="Näkymä tarratulostussivulta" style="width:100.0%" />

*Valitse lista* -valikon *Oma tulostusjono* -valinnalla saa listan kaikista niteistä, jotka käyttäjä on vienyt nidenäytöllä tulostusjonoon. Ks. ohje alla.
*Tänään vastaanotetut* -valinta tuo listan kaikista kyseisenä päivänä kirjautusmiskirjastossa vastaanotetuista niteistä.
*Itse tulostetut* -valinta tuo listan kirjautuneen käyttäjän aiemmin tulostamista niteistä.

Nämä valikosta tulevat viivakoodit pitää siirtää mustasta nuolesta oikealle tulostettavaksi. *Lisää kaikki* -napilla saa siirrettyä kaikki kerralla. Punainen ruksi poistaa viivakoodit pysyvästi listoilta. *Oma tulostusjono* ja *Tänään vastaanotetut* -listat tyhjenevät pysyvästi, kun niillä olevat viivakoodit tulostaa.

<img src="/assets/files/docs/Tyokalut/tulostus1.png" title="Näkymä tarratulostussivulta" alt="Näkymä tarratulostussivulta" style="width:100.0%" />

Kun halutut niteet ovat oikealla *Tulostettavat niteet* -listalla, paina *Tulosta*, jolloin aukeaa esikatselu. Siinä voi vielä säätää ylä- ja vasenta marginaalia. Oikeat arvot selviävät kokeilemalla. Arvot pysyvät selaimen muistissa, kunnes selaimen välimuistin tyhjentää.

<img src="/assets/files/docs/Tyokalut/tulostus2.png" title="Näkymä tarrojen esikatselusta, jossa voi määrittää ylä- ja vasemman marginaalin" alt="Näkymä tarrojen esikatselusta, jossa voi määrittää ylä- ja vasemman marginaalin" style="width:100.0%" />

Painamalla *Tulosta* muodostuu tulostettava PDF-tiedosto. *Takaisin*-napista pääsee takaisin edelliselle näytölle ja tulostettavat niteet pysyvät vielä tallessa.

**Niteiden lisääminen omaan tulostusjonoon**

Lisää halutut niteet *Perustiedot*-näytöltä tarratulostusjonoon. Laita rasti haluamiesi niteiden kohdalle, jolloin näkyville tulee nidetaulukon yläpuolelle linkki *Lisää valitut niteet tulostusjonoon*, jota klikkaamalla niteet saa vietyä omaan tulostusjonoon Tarratulostustyökalussa.

<img src="/assets/files/docs/Tyokalut/tulostusjonoon_uusi.png" title="Näkymä perustiedot-sivulta, jossa määritetään nide tulostusjonoon Lisää valitut niteet tulostusjonoon -linkillä" alt="Näkymä perustiedot-sivulta, jossa määritetään nide tulostusjonoon Lisää valitut niteet tulostusjonoon -linkillä" style="width:100.0%" />

Jos tulostettavia niteitä on kahdella eri välilehdellä (oman kirjaston kokoelmat ja muut kokoelmat), pitää kummallakin välilehdellä tehdä valinta ja vienti erikseen.

Kannattaa hyödyntää Kokoelmat-taulukon suodatus-toimintoa ja suodattaa näkyville vain halutut niteet ja sen jälkeen *Valitse kaikki*, jolloin näkyvillä olevat niteet tulevat valituksi ja ne saa vietyä kerralla tulostusjonoon.

Myös niteiden muokkaustilassa niteen voi listätä tulostusjonoon joko muokattavan niteen lomakkeen alta *Tulostusjonoon*-napista tai nidetaulukon *Toiminnot*-valikon *Tulostusjonoon*-kohdasta. Jokainen *Tulostusjonoon*-napin painallus vie viivakoodin tulostusjonoon. Saman niteen voi siis näin viedä useampaan kertaan, jos sellaiseen on tarvetta esim. av-aineiston osalta.

<img src="/assets/files/docs/Tyokalut/tulostusjonoon1.png" title="Näkymä niteiden muokkauksesta, jossa määritetään nide tulostusjonoon" alt="Näkymä niteiden muokkauksesta, jossa määritetään nide tulostusjonoon" style="width:70.0%" />

<img src="/assets/files/docs/Tyokalut/tulostusjonoon2.png" title="Näkymä niteiden muokkauksesta, jossa määritetään nide tulostusjonoon" alt="Näkymä niteiden muokkauksesta, jossa määritetään nide tulostusjonoon" style="width:100.0%" />

**Huomioi**, että pdf-ohjelman tulostusasetuksista kannattaa aina
valita, ettei skaalata tai soviteta arkin kokoon. Jos käytetään
skaalausta, se muuttaa tarrojen asemointia myös suhteessa toisiinsa,
jolloin ne eivät enää osu oikeaan kohtaan arkkia (esim. liian lähelle
tai kauas ylempänä olevasta tarrasta).

---

### Ohje tarrapohjan muokkaajalle

Ohje tarrapohjan muokkaajalle löytyy liitännäisen ohjesivulta:
[Tarrapohjan muokkaaminen](https://github.com/KohaSuomi/koha-plugin-visual-label-tool#how-create-and-modify-labels)

---

## 12.10 Siirtokokoelmat

Siirtokokoelmaan lisätyt niteet palautuvat aina siihen kirjastoon, johon ne on siirretty. Niteiden kotikirjasto ei muutu. Perustiedot-näkymässä ei näy, että nide kuuluu johonkin siirtokokoelmaan.

Huom. Järjestelmäasetuksen *AutomaticItemReturn* arvon tulee olla *Älä kuljeta niteitä automaattisesti kotikirjastoon, kun ne palautetaan*, jotta siirtokokoelma toimii.

**Siirtokokoelman luominen**

Luo uusi siirtokokoelma painamalla *Uusi kokoelma* -painiketta siirtokokoelmien etusivulla, täytä nimeke ja kuvaus ja paina *Ok*.

<img src="/assets/files/docs/Tyokalut/siirtokokoelma1.png" title="Lisää uusi kokoelma -näkymä, jossa kysytään nimekettä ja kuvausta" alt="Lisää uusi kokoelma -näkymä, jossa kysytään nimekettä ja kuvausta" style="width:50.0%" />

Sen jälkeen lisää niteitä kokoelmaan syöttämällä niteen viivakoodi kenttään ja paina *ok*.

<img src="/assets/files/docs/Tyokalut/siirtokokoelma2.png" title="Lisää tai poista niteitä -näkymä, jossa kysytään niteen viivakoodia" alt="Lisää tai poista niteitä -näkymä, jossa kysytään niteen viivakoodia" style="width:50.0%" />

Siirtokokoelmien pääsivulla lisää niteitä kokoelmaan painamalla halutun siirtokokoelman kohdalla *Toiminnot*-nappia ja valitsemalla *Hallinnoi niteitä*. 

<img src="/assets/files/docs/Tyokalut/siirtokokoelma3.png" title="Toiminto-valikko siirtokokoelmien pääsivulla" alt="Toiminto-valikko siirtokokoelmien pääsivulla" style="width:100.0%" />

**Kokoelman siirtäminen**

Kokoelma siirretään haluttuun kirjastoon joko painamalla pääsivun *Toiminnot*-painikkeen takaa *Siirto* tai tietyn siirtokokoelman sivulla *Siirto*-nappia. Kummassakin tapauksessa valitaan seuraavaksi kirjasto, johon niteet ovat menossa. Siirto vahvistetaan *Siirtokokoelma*-painikkeella. 

Vastaanottavan kirjaston tulee palauttaa kaikki siirtokokoelman niteet. 
Jos siirtokokoelman nide palautetaan jossain toisessa kirjastossa, pyytää Koha palauttamaan niteen kirjastoon, johon siirtokokoelma on luotu ja kertoo että kyseessä on siirtokokoelmaan kuuluva nide.

**Kokoelman poistaminen**

Kokoelmassa olevat niteet on poistettava ennen siirtokokoelman poistamista. Avaa siirtokokoelma painamalla halutun siirtokokoelman nimeä. 
Poista niteet joko lukemalla siirtokokoelmasta poistettavan niteen viivakoodi ja ruksimalla *Poista nide kokoelmasta* tai painamalla kyseisen niteen kohdalla *Poista*. 

<img src="/assets/files/docs/Tyokalut/siirtokokoelma4.png" title="Toiminto-valikko siirtokokoelmien pääsivulla" alt="Toiminto-valikko siirtokokoelmien pääsivulla" style="width:80.0%" />

Kun kaikki siirtokokoelman niteet on poistettu, voit poistaa kokoelman painamalla pääsivun *Toiminnot*-painikkeen takaa *Poisto* tai tietyn siirtokokoelman sivulla *Poisto*-nappia. 



