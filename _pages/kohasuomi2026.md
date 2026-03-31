---
title: 'Koha-Suomen vuoden 2026 muistiot'
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
permalink: /kohasuomi2026
redirect_from:
  - /theme-setup/
toc: true
layout: single
hidden: true
---

## Viikko 13

Aika: Ma 30.3.2026<br />
Läsnä: Ari, Lari, Johanna, Anneli, Emmi, Pasi, Kodo

* Vastuuttomat tiketit
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Asioiden kirjaaminen palaverimuistioon on jäänyt retuperälle, kuinka tätä tilannetta voitaisiin parantaa ja missä laajuudessa asioita on hyvä kirjata? Nyt tehtyjen muutosten seuraaminen on hankalaa.
  * Kehittäjät kirjaavat tähän muistioon muiden tiedoksi asiat koko viikon ajalta.
* Päivitys ajetaan maanantai-iltana
* Anneli:
  * Tietuenäyttöjen mukautuksista raportoitiin ongelmia kentän 020q-osalta. Ongelma johtui siitä, että Template Toolkit -sääntö ei huomioinut sitä, että q-osakenttä voi toistua. Laitettu testattavaksi toistot huomioiva versio
  * Kuvailusääntöihin on tehty muutos, jossa 800t-osakenttään aletaan kirjaamaan sarjan nimekkeen perään tieto "(teksti : nide)". Tämä rikkoo Sarja-tiedon hakulinkin, koska sarjaa haetaan t-kentän sisällön mukaisesti, esim. Myrskylän retket (teksti : nide). Kaikissa tietueissa ei kuitenkaan ole tuota uuden kuvailusäännön mukaista lisätietoa, joten ne eivät osu hakuun. Koitin ratkoa ongelmaa lisäämällä tietuenäyttöjen mukautus -työkalulla uuden Sarja-otsikon, joka tekee hakulinkin ilman tuota (teksti : nide) -lisäystä. Sain sen toimimaan, mutta huomasin sen jälkeen, että kuvailusääntöjen mukaan 800t-kenttään voidaan lisätä tietoja myös vähän toisessa muodossa, jos kyseessä on erikielisiä teoksia, esim. (teksti: nide : ruotsi). Tämä tieto tarkoittaa, että nykyinen regex ei toimi. Lisäksi ilmeisesti sarjatietoa haetaan myös 490-kentästä niissä tapauksissa, että sarjaan ei liity tekijää, eli silloin ei tehdä ollenkaan 800-kentän kirjausta. Tämä vaatii siis vielä pohdintaa.
  * Eräpäivän siirto -työkalussa on ongelmana, että se näyttää esikatselussa uuden eräpäivän vain noin puolelle valituista. Eräpäivä kyllä muuttuu kaikille, vaikka tieto puuttuukin esikatselusta.
  * Oulussa oli ongelma maksujen viennissä Ceepos-kassaan. Se epäonnistui välillä. Syyksi paljastui asiakkaan Lainaus-sivulla oleva Huomioi-kentän Maksa kaikki maksut -nappi, joka vei sellaiseen näkymään, jossa maksujen vienti Ceepokseen ei onnistu, koska osoitteessa ei ole mukana yksittäisten maksujen accountline_id:t. Pikakorjauksena kielletty käyttää kyseistä nappia ja Lari tekee kestävämmän korjauksen suoraan Ceepos-liitännäiseen eli piilottaa kyseisen nappulan.
  * Lastussa oli lähtenyt asiakkaalle palautuskehotus, jossa ei ollut item-tägin sisälle muodostunut teostietoja. Epäilin ensin, että asiakas on ehtinyt palauttaa niteen siinä välissä, kun viesti on luotu, mutta ei vielä lähetetty. Teokset oli kuitenkin palautettu vasta viestin lähetyksen jälkeen, joten tämä teoria ei pitänyt paikkansa. Tämä saattaa jäädä mysteeriksi, koska muita vastaavia tapauksia ei message_queuesta löytynyt.
  * OUTIssa ei ollut lähtenyt MEMBERSHIP_EXPIRY-viestejä. Todennäköinen syy on viestipohjassa ollut Template Toolkit -koodissa ollut virhe.
  * Kyytistä ihmeteltiin, että Vanhentuneet varaukset -raportille ei tule enää tuloksia sen jälkeen kun ExpireReservesOnHolidays-järjestelmäasetukseen muutettiin heillä, että varausten ei sallita vanhentua kiinniolopäivinä (esim. viikonloppuisin). Raportti on kuitenkin rakennettu niin, että varaus on poistettu seuraavana päivänä sen expirationdatesta. Muuten siihen tulee mukaan muitakin kuin vanhentumisskriptin poistamia.
* Johanna
  * Tarratulostustyökalu: Käännösten lisääminen liitännäiseen rikkoi muokkauksessa virheviestien näkymisen. Samalla parantelin virheviestejä, jotta niistä ymmärtäisi paremmin mikä on vikana. https://github.com/KohaSuomi/koha-plugin-visual-label-tool/issues/11
  * Tulosta ilmoituksia -liitännäisessä peruuta-painiketta painaessa sivu ei päivity automaattisesti: Tähän viety korjaus testeille, vaatii vielä parantelua. https://github.com/KohaSuomi/Koha/issues/2221
  * Lapille aktivoitu kaukolainamoduulia testeille. https://github.com/KohaSuomi/Koha/issues/2216
  * Vaskille vietu noutohyllyt nexteiltä testeille, https://github.com/KohaSuomi/Koha-25x/issues/252 ja OUTI:lle tyhjennetty noutohyllytaulut.    
* Emmi
  * Kirkesiin ajettu cn_sort-kenttien korjaus https://github.com/KohaSuomi/Koha/issues/2024
  * Testeille tehty muutoksia indeksointijonon kokoon ja muutos dokumentoitu

## Viikko 12

Aika: Ma 16.3.2026<br />
Läsnä: Lari, Anneli, Johanna, Aleksi, Pasi, Ari, Kodo, Emmi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

## Viikko 11

Aika: Ma 9.3.2026<br />
Läsnä: Ari, Emmi, Johanna, Aleksi, Lari, Kodo, Pasi

* Päivystysvuorot viikosta 12 alkaen
* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Versionvaihdon tilannekatsaus, testien versionvaihtoon viikko

## Viikko 10

Aika: Ma 2.3.2026<br />
Läsnä: Ari, Emmi, Johanna, Aleksi, Lari, Anneli, Kodo

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)


## Viikko 9

Aika: Ma 23.2.2026<br />
Läsnä: Anneli, Ari, Lari, Kodo, Emmi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

## Viikko 8

Aika: Ma 16.2.2026<br />
Läsnä: Ari, Emmi, Johanna, Kodo, Anneli, Lari, Pasi

* Päivystysvuorot vko 9 eteenpäin
* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Versionvaihdon tilannekatsaus, kun versionvaihtoon reilu kuukausi.
  * [Auki olevat tiketit](https://github.com/KohaSuomi/Koha-25x/issues)
  * [Avoimet tiloittain](https://github.com/orgs/KohaSuomi/projects/6/views/2)

## Viikko 7

Aika: Ma 9.2.2026<br />
Läsnä: Ari, Pasi, Lari, Emmi, Johanna, Kodo

* Vko 7 päivitys
  * Koha-tietoturvapaikka, tuotantoon tiistaina 10.2. aamulla.
* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* IntranetUserJS-rimpsujen päivitykset
  * Pääkäyttäjät tekee varsinaisen muutoksen, Koha-Suomen päivystäjä laskee uuden tarkisteen.
  * Tehdään ohjeistus (Emmi), päivitetään principio (Kodo)
* Meitä kiinnostavien yhteisö-tikettien koostaminen esim. Bugiton-tietovarantoon.
  * Avataan tiketti bugittomaan ja siihen linkki bugzillaan.
* OUTIn signum-kuvio
  * Käytetään asiantuntijaryhmässä, saataisiinko yhtenäinen käytäntö
  * Otettanee plugin matkaan tilapäisesti, työ on Outille maksullista

## Viikko 6

Aika: Ma 2.2.2026<br />
Läsnä: Ari, Anneli, Lari, Johanna, Kodo, Pasi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

## Viikko 5

Aika: Ma 26.1.2026<br />
Läsnä: Ari, Anneli, Kodo, Emmi, Johanna, Lari, Pasi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Rajapintojen salasanojen/tokenien kierrättäminen ulkoisissa palveluissa.
  * Pyydetään pääkäyttäjiä miettimään mitkä mahdolliset palvelut, ja uusimaan niiden salasanat säännöllisesti. 


## Viikko 4

Aika: Ma 19.1.2026<br />
Läsnä: Johanna, Pasi, Kodo, Ari, Lari ja Emmi

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
* Versionvaihdon tilannekatsaus, kun laajemmat testaukset ovat olleet käynnissä viikon.
  * [Auki olevat tiketit](https://github.com/KohaSuomi/Koha-25x/issues)
  * [Avoimet tiloittain](https://github.com/orgs/KohaSuomi/projects/6/views/2)

## Viikko 3

Aika: Ma 12.1.2026<br />
Läsnä: Pasi, Anneli, Emmi, Ari, Lari, Johanna, Kodo

* Vastuuttomat tiketit
  * [ei-Koha25x-tiketit](https://github.com/issues?q=is%3Aopen%20is%3Aissue%20owner%3AKohaSuomi%20archived%3Afalse%20sort%3Aupdated-desc%20no%3Aassignee%20-repo%3AKohaSuomi%2FBugiton%20-repo%3AKohaSuomi%2FFinna-kehitysehdotukset%20-repo%3AKohaSuomi%2FKoha-25x)
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)
