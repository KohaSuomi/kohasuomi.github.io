---
title: 'Järjestelmäasetukset'
permalink: /dokumentaatio/jarjestelmaasetukset/
redirect_from:
  - /theme-setup/
toc: true
---

## Ohjeita ja tietoja eri järjestelmäasetuksista

Koha-yhteisön suositus on, että auktorisoitujen arvojen koodeihin, esim. kirjastojen, hyllypaikkojen, yms. lyhenteisiin kannattaa käyttää vain kirjaimia a-z ja numeroita 0-9. Muut merkit voivat aiheuttaa ongelmia Kohan ja indeksoinnin kanssa.

Lisäksi koodeissa ei kannata olla myöskään alaviivoja, koska ne voivat aiheuttaa ongelmia indeksin kanssa.

Koska järjestelmäasetuksia on satoja, ei kaikista ole tällä sivulla tietoja. Järjestelmäasetuksia on käyty läpi pääkäyttäjien kanssa ja läpikäynneistä on tallenteet [Koha-Suomen Youtube-kanavalla](https://www.youtube.com/@koha-suomi/videos).

### ActionLogsTraceDepth

Asetuksella saa tallennettua action_logs-tauluun uuteen trace-sarakkeeseen tarkemmin tiedon, missä päin Kohaa toiminto on tehty.

action_id | timestamp | user | module | action | object | info | interface | script | trace
-- | -- | -- | -- | -- | -- | -- | -- | -- | -- 
34 | 2023-08-22 10:01:04 | 51 | CIRCULATION | RETURN | 19 | 193 | intranet |   | [{"line":2476,"package":"C4::Circulation","subroutine":"C4::Log::logaction","filename":"/kohadevbox/koha/C4/Circulation.pm"},{"package":"CGI::Compile::ROOT::kohadevbox_koha_circ_returns_2epl","line":359,"subroutine":"C4::Circulation::AddReturn","filename":"/kohadevbox/koha/circ/returns.pl"},{"filename":"/kohadevbox/koha/circ/returns.pl","subroutine":"(eval)","package":"CGI::Compile::ROOT::kohadevbox_koha_circ_returns_2epl","line":2}]
35 | 2023-08-22 10:01:44 | 51 | CIRCULATION | ISSUE | 19 | 193 | intranet |   | [{"subroutine":"C4::Log::logaction","filename":"/kohadevbox/koha/C4/Circulation.pm","line":1806,"package":"C4::Circulation"},{"subroutine":"C4::Circulation::AddIssue","filename":"/kohadevbox/koha/circ/circulation.pl","package":"CGI::Compile::ROOT::kohadevbox_koha_circ_circulation_2epl","line":402},{"package":"CGI::Compile::ROOT::kohadevbox_koha_circ_circulation_2epl","line":2,"filename":"/kohadevbox/koha/circ/circulation.pl","subroutine":"(eval)"}]

Asetukseen asetetaan numero sen mukaan, kuinka "syvälle" halutaan seurata. Esimerkissä taso on 3.

**Suositus**: Tuotannossa 0 eli pois päältä. Tarvittaessa ongelmia etsittäessä testikantaan taso 2, mutta sinnekin normaalitilanteessa 0.


### BarcodePrefix

Asetuksella voi määrittää, millä merkkijonolla automaattisesti generoidut viivakoodit alkavat. Tämä vaatii kaveriksi autoBarcode-asetuksen toimiakseen. Asetus on YAMLia eli tieto pitää tallentaa tietyssä muodossa. Ensin kirjoitetaan kirjaston tunnus (minkä kirjaston niteestä kyse) - kaksoispiste - välilyönti - haluttu prefix. Eli siis näin:

LAPK: 111N<br />
TUPK: 123N<br />
RAPK: OUTI<br />

Eri kirjastopisteet laitetaan omille riveille.

### IntranetFavicon

IntranetFavicon-järjestelmäasetuksessa voi määrittää, minkälainen ikoni näytetään selaimessa välilehden otsikossa. Asetukseen voi määrittää kuvatiedoston base64-muodossa, kun asetukseen määrittää näin:

```
data:image/png;base64, iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAAAXNSR0IArs4c6QAAAA lwSFlzAAALEwAACxMBAJqcGAAAAVlpVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADx4 OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IlhNUCBDb3 JlIDUuNC4wIj4KICAgPHJkZjpSREYgeG1sbnM6cmRmPSJodHRwOi8vd3d3LnczLm9y Zy8xOTk5LzAyLzIyLXJkZi1zeW50YXgtbnMjIj4KICAgICAgPHJkZjpEZXNjcmlwdG lvbiByZGY6YWJvdXQ9IiIKICAgICAgICAgICAgeG1sbnM6dGlmZj0iaHR0cDovL25z LmFkb2JlLmNvbS90aWZmLzEuMC8iPgogICAgICAgICA8dGlmZjpPcmllbnRhdGlvbj 4xPC90aWZmOk9yaWVudGF0aW9uPgogICAgICA8L3JkZjpEZXNjcmlwdGlvbj4KICAg PC9yZGY6UkRGPgo8L3g6eG1wbWV0YT4KTMInWQAABLJJREFUWAnFV+trW2UY/yVN0j S32q6bnWunQ1e11k3YXMUy8AbDoSBDv4mfFPTj/gD9ug/7B/woqCCISnGItcyppbgN Rhn2st5G2yxt1svSJe1yPYnP703fcs7JSZo4YS9Ncs57eX6/5/Y+T12fX7hYdAHy92 iG+1GCU2X3/6V3k9sNl8uFUqnUkMiHJkDfuQV4M7WFbC4Hr8fTEAlPQ3RtmwleFI0z mQxO95/EQP8pLEaj+PaHQbS3RmAUi7YTla8PRYDGLhgGPnz/HI719Srp0VgMhszRHf WM/+wC+jy1tY2zb72uwOl7WmPi1gwCfr887609CdZtAfpZa0XNc/k8nug8gBPHjylF uTY7N4/JmVmEQkFlBbWwx9eeBNyiKbVLZ7IKlEAtomEmm0Vvz1G0tLQoiKXoHXzz/Y 9qX75QgM/jhb/ZB5KtlRk1CdDM2+k0SKLn6SM4KBoXRHhsOY6J2XmsbWxgdv42Jqdn cH3sJo4c7sKhg50oFku4s7yMuYUleJqahEizzDm7pCoBgt8XH7/Q8wzOvPmamLtz1w UMvPjdu1hYjIrPp9He9hjOf/oJ9rW37e5hBiwuRXFpaBjR5RWEgkFHEq4vLlysuDkI nhTwV068hPfeOau0oJ21KXUsKNvbvux7suKq734axNT0nLhOLCHuNI8KC1B4Wg7RnO ++fUaB03x0gxlYA1EYZcoxta73cJ3PD8SFuWxOnbdCl2k4EuCN9sbpATT7fMpsBLcP DcR5gpuHBk8mU/jyq6+xcW8TYckMpziwSKagvKTX4x0deOpwt5JpBjKD1PM8eu064q vraI2EHcEpw0pAqnK+YODA/n3wS6pxNEpAa58TK05IdoQl+AyjoGQ5fVkI0JbFoqEi tlFgu/C01IeM3B2UY4s7y1YrAbXUeEm1SNx58Un8sDJKiNbsdiwEaD6m4JakoFPAOA HZ57TleFs+2d2lMsotl1G1YSHATR5PEzYSCXXt8p2kGh36zED/y+o8qyNridOwEOBB j5htI7GJ1bU1p/11zZX9XkJ31yF89MG5nTpScAxoCwFKZ86z8NxeWKwLrNom7YrjL/ bh/GcfY39Hu2RYJYkKAvR9KBjAjZv/CJHMThQ37gYS066IhMNgWmpSZtIVBHio2euV AhLH+OSU2qsFmQ828jx69Rpi8VX4vJX9YgUBCmbBCIsVhv8cQTKVKt/jDsFIYvpjJ0 RLUuPYygqujF5FG3tEo7IkOxKgUObwvcR9DF2+omRTmE5NDco5/dFzSoGd4sWaMvjL kCJZJQmsV7FZC9bziBSQv2+M4Y+RUbWki5IGZXPC1oy/eo4buY9W/PnX3zC/uFTuEa VJcRoV1dC8iSRawyFcGv4dqe1tvHrqpFS1EFbX1zE+dQvT0hVlpNSyzvc+exR9zz8n zUmbVL8ELv81grHxSbTK/lrtuWNDYibBZ14iSSEQlP6PGbIpZTadzkg/6Fdr1PaBvI cCLYgIYa7TKsFAYNdtdpn6vaYF9CYCREQTxkBS/gPySZb42SvIvDhYNQRsQBlkal3i R/cSWka137oI8LAOQF7VDDiDwHrw3Si/l9eFl5CtZzhmQa2DZlynfXut28/8C/JOMz 7+5SRKAAAAAElFTkSuQmCC
```

Kuvan pystyy muuttamaan base64-muotoon verkosta löytyvillä konverttereilla. Vaihda esimerkkiin oman ikonisi base64-koodi ennen kuin laitat sen järjestelmäasetukseen.

### IntranetNav

IntranetNav-järjestelmäasetuksella saa lisättyä Kohan yläpalkkiin linkkejä. Alla viimeisin versio, jolla saa lisättyä Koha-Suomi-alasvetovalikon:

```
<li class="dropdown pull-right"><li class="nav navbar-nav pull-right"><a href="
<li id="kohasuomi-navlinkit" class="dropdown pull-right">
  <a href="/cgi-bin/koha/mainpage.pl" class="dropdown-toggle" data-toggle="dropdown">Koha-Suomi <b class="caret"></b></a>
  <ul class="dropdown-menu dropdown-menu-left">
    <li><a href="https://koha-suomi.fi/dokumentaatio/ohjeet/
" target="_ohjeet">Koha-ohje</a></li>
<li><a href="https://github.com/KohaSuomi/Koha/discussions
" target="_tiedotteet">Tiedotteet</a></li>
<li><a href="https://koha-suomi.fi/muistiot
" target="_muistiot">Muistiot</a></li>
<li><a href="https://github.com/orgs/KohaSuomi/projects/4
" target="_tiketit">Tiketit</a></li>
 </ul>
</li>
```

### IntranetReportsHomeHTML

Järjestelmäasetukseen voi lisätä omaa tekstiä Raporttien etusivulle. Sinne on päätetty siirtää Koha-Suomen MARC-virheraporttien linkit. Ne pystyy lisäämään alla olevan esimerkin mukaisesti. Muokkaa kimpan nimi osoitteisiin (huomaa, että kimpan nimi on osoitteessa kaksi kertaa eli yhteensä neljä muutosta)

```
<div class="col-md-10 col-md-offset-1 col-lg-8 col-lg-offset-2">
<h2>MARC-virheraportit</h2>
<ul>
<li><a href="https://helle.koha-suomi.fi/marc_virheet.helleprod.html" target="_blank" rel="noopener">Virheelliset tietueet </a></li>
<li><a href="https://helle.koha-suomi.fi/marc_virhemaara.helleprod.txt" target="_blank" rel="noopener">Virhem&auml;&auml;r&auml;t</a></li>
</ul>
</div>
```

### IntranetUserCSS

IntranetUserCSS-järjestelmäasetuksella voi "ohittaa" Kohan omia CSS-määrityksiä ja tehdä esimerkiksi erilaisia piilotuksia. Alla on linkki CSS-kirjastoon.

[IntranetUserCSS-kirjasto](/dokumentaatio/intranetusercss/)

### IntranetUserJS

IntranetUserJS-järjestelmäasetukseen voi lisätä JavaScript-koodeja, joille voi esim. lisätä tietoja eri näytöille kuten henkilötunnuksen lisäyskenttä asiakkaan muokkauksessa. Järjestelmäasetuksen muokkaamiseen tarvitaan kehittäjien apua, lue tarkemmat ohjeet alla olevasta JS-kirjastosta.

[IntranetUserJS-kirjasto](/dokumentaatio/intranetuserjs/)

### PrepareHostField

PrepareHostField-järjestelmäasetuksella voi määrittää, mistä emotietueen kentistä siirretään tietoja osakohteen 773-kenttiin, kun emotietueelle luodaan uusi osakohde.

```
001: 773$w
020$a: 773$z
022$a: 773$x
028$ba: 773$o
245$abnpc: 773$t
260$ab: 773$d
264$abc: 773$d
300$ae: 773$h
```

### SCOUserCSS

SCOUserCSS-järjestelmäasetuksella voi säätää Kohan itsepalvelulainauksen ulkoasua.

Vaara-kirjastojen versio:

```
.navbar {
	display: none;
}

#opacheader {
	display: none;
}

.sco_entry.col-5 {
  background-color: rgb(81, 163, 226);
  margin: 25px 25px 55px 55px;
  padding: 25px 25px 25px 25px;
  -webkit-border-radius: 10px;
-moz-border-radius: 10px;
border-radius: 10px;
-webkit-box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35); 
box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35);
}

.sco_entry.col-5 h4 {
 font-size: 25px;
 color: darkslategrey;
}


.sco_entry.col {
  background-color: rgb(179, 222, 122);
  margin: 25px 25px 55px 55px;
  padding: 25px 25px 25px 25px;
  -webkit-border-radius: 10px;
-moz-border-radius: 10px;
border-radius: 10px;
-webkit-box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35); 
box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35);
}

.sco_entry.col h4 {
 font-size: 25px;
 color: darkslategrey;
}


#newcheckout {
  background-color: rgb(81, 163, 226);

  padding: 25px 25px 25px 25px;
  -webkit-border-radius: 5px;
-moz-border-radius: 5px;
border-radius: 5px;
-webkit-box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35); 
box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35);
}

.sco_entry h2 {
 font-size: 25px;
 color: darkslategrey;
}

#account {
 display: none;
}

label {

  white-space:nowrap;
}


#uibarcode {
  			
            width: 116%;
  
        }

.alert.alert-info {
  			background-color:rgb(0, 241, 111);

  
        }

/*  .alert.alert-info::after {content: "  Kirjautumisen jälkeen istunto katkaistaan 40 sekunnin kuluttua. Kirjaudu sisään uudelleen tarvittaessa.";}
*/
```

OUTI-kirjastojen versio:

```
a#account.nav-link { display: none; }

.navbar {
	display: none;
}

#opacheader {
	display: none;
}

.btn.btn-info.btn-sm.return{
  display: none;
}

.sco_entry.col-5 {
  max-width: 500px;
  background-color: skyblue;
  margin: 25px 25px 55px 55px;
  padding: 25px 25px 25px 25px;
  -webkit-border-radius: 10px;
-moz-border-radius: 10px;
border-radius: 10px;
-webkit-box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35); 
box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35);
}

.sco_entry.col-5 h4 {
 font-size: 25px;
 color: black;
}


.sco_entry.col {
  max-width: 500px;
  background-color: #8fe67e;
  margin: 25px 25px 55px 55px;
  padding: 25px 25px 25px 25px;
  -webkit-border-radius: 10px;
-moz-border-radius: 10px;
border-radius: 10px;
-webkit-box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35); 
box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35);

}

.sco_entry.col h4 {
 font-size: 25px;
 color: black;
}


#newcheckout {
  background-color: skyblue;
  max-width: 400px;
  padding: 25px 25px 25px 25px;
  -webkit-border-radius: 10px;
-moz-border-radius: 10px;
border-radius: 10px;
-webkit-box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35); 
box-shadow: 5px 5px 7px 0px rgba(0,0,0,0.35);
}

.sco_entry h2 {
 font-size: 25px;
 color: black;
}

#account {
 display: none;
}
```
### SCOUserJS

```
/* Viivakoodinlukijoita varten PINillä kirjautuessa: */
/* Hitting "Enter" key in the username field will jump focus to the password field instead of submitting form  */
$(document).ready(function(){
    $('#patronlogin').keypress(function(e){
        if (e.keyCode == 13){
            $('#patronpw').focus();
            return false;
        }
    }); 
});
```

### Yksittäisiin asetuksiin suosituksia

Asetus|Suositus|Lisätietoja
---|---|---
AgeRestrictionOverride | Älä salli | Esim. elokuvien ja pelien ikärajat ovat sitovia
autoControlNumber| ei generoida tietuenumerona | Tähän asetukseen liittyy isoja ongelmia, joten tätä ei suositella laitettavaksi päälle. Ongelmia on mm. tietueiden tuonnissa välivarastosta ja Z39.50-haulla. Asetuksen ollessa päällä 001-kenttä tyhjenee ja korvautuu biblionumberilla. Näin ei pitäisi manuaalin mukaan käydä vaan vanha arvo säilytetään, jos sellainen on olemassa. [Bugi Bugzillassa](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41158). Meillä on käytössä oma Add MARC field 001 -liitännäinen, joka suositellaan aktivoitavaksi tämän asetuksen sijaan.
CalculateFinesOnReturn | Älä laske | Myöhästymismaksut lasketaan yöllä ajastetulla ajolla. Jos tämäkin on päällä, maksut voivat kirjautua asiakkaalle tietyissä tilanteissa uudelleen [maksut maksetaan ja sitten sen jälkeen palautetaan myöhässä olevia niteitä].
CancelOrdersInClosedBaskets | Salli | Asetuksella määritetään, voiko suljettujen tilauskorien tilauksia perua. Jos tähän laittaa, että voi perua, ei tarvitse ensin avata tilauskoria ensin.
ChargeFinesOnClosedDays | Laskuta | Asetuksella määritetään, lasketaanko myöhästymismaksut kalenteriin merkittyinä sulkupäivinä. Käytännössä tähän kannattaa laittaa Laskuta, jotta myöhästymismaksut olisivat aina ajan tasalla. Myöhästymismaksut lasketaan seuraavana aukiolopäivänä siten, että myös sulkupäivät laskutetaan, joten asiakkaalle voi näyttää siltä kuin maksua olisi kertynyt kerralla liikaa.
CircControl | the library the item is from | Asetuksella säädetään, minkä kirjaston laina- ja maksusääntöjä käytetään. Lisäksi pitää määrittää HomeOrHoldingBranch-asetus, jossa määritetään, käytetäänkö niteen koti- vai sijaintikirjastoa.
DefaultPatronSearchMethod | Sisältää | Asetuksella määritetään, käytetäänkö asiakashaussa Alkaa- vai Sisältää-hakua.
finnaprefix |esim. outi. | Asetukseen laitetaan kimpan Finna-tietueiden tunniste, joka on osoitteessa ennen tietuenumeroa. Esim. OUTIssa https://outi.finna.fi/Record/**outi.**2255834 ja Siilinjärvellä https://siilinjarvenkirjasto.finna.fi/Record/**siilinjarvi.**130457. Tietoa käytetään, kun viedään raportin tulokset JSON-muotoon. Asetus löytyy Paikalliset asetukset -osiosta, johon järjestelmäasetusten haku ei yllä.
ItemsDeniedRenewal | notforloan: [6] | Estää laskutetun niteen uusimisen
HidePersonalDetailOnCirculation | Piilota | Vältetään turhia tietojen katseluja
HoldsNeedProcessingSIP | Älä täytä | Omatoimiaikana automaattiin palautetuista varatuista niteistä ei lähde näin noutoilmoituksia
HomeOrHoldingBranch | the item’s holding library (holdingbranch) | Asetuksella määritetään, onko CircControlissa määritetty kirjastotieto niteen koti- vai sijaintikirjasto.
LockExpiredDelay | Jätä tyhjäksi | Jos tässä asetuksessa on arvo, cleanup_database-cronajo asettaa vanhentuneille asiakkaille borrowers-tauluun login_attempts-sarakkeeseen arvon -1 eli "Tili on lukittu hallinnollisesti". Cronajo ei ole normaalisti käytössä, mutta sitä saatetaan joutua käyttämään välillä, joten asetuksen arvo kannattaa jättää tyhjäksi, jolloin toiminto ei ole käytössä.
PatronAutoComplete | Älä ehdota | Vältetään turhia tietojen katseluja
SearchEngine| ElasticSearch |
StoreLastBorrower | Säilytä | Säilytetään erillisessä taulussa niteen viimeisin lainaaja, vaikka lainat anonymisoidaan. Auttaa löytämään oikean asiakkaan ongelmatilanteissa.
StripWhitespaceChars | Poista | Asetuksella voi määrittää poistetaanko kuvailutietueen MARC-kentistä ylimääräiset välilyönnit, sarkaimet ja rivivaihdot. Asetus ei vaikuta kiinteämittaisiin kenttiin. [StripWhitespaceChars](https://koha-community.org/manual/23.05/en/html/catalogingpreferences.html#stripwhitespacechars)
TrackLastPatronActivityTriggers | Kaikki muut paitsi Artikkelipyyntöä tehdessä | Asetuksella valitaan, mitkä tapahtumat päivittävät asiakkaan lastseen-arvon. Aina kun valitut tapahtuu, päivitetään asiakkaan lastseen-arvo sen hetkisellä päivämäärällä ja kellonajalla.
TransfersBlockCirc | Estä | Kuljetukseen on reagoitava
TrapHoldsOnOrder | Ota kiinni | Saapunut/tilattu-tilaiset jäävät palautuksessa varauksiin kiinni
UpdateNotForLoanStatusOnCheckin | 6 : ONLYMESSAGE | Laskutetusta niteestä tulee ilmoitus palautettaessa




