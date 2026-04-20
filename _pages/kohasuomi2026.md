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

Muistioiden laadinnassa voidaan hyödyntää huhtikuusta 2026 alkaen kielimalleihin ja GitHub APIin perustuvaa automaatiota. Muistiot kuitenkin tarkistetaan Koha-Suomen henkilökunnan toimesta.

## Viikko 17
Aika: Ma 20.4.2026<br />
Läsnä:

### Vastuuttomat tiketit
* [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

### Muut asiat
* [Viikon 17 päivitys](https://github.com/orgs/KohaSuomi/projects/4/views/11)
* [KohaCon26-ilmoittautuminen](https://kohacon26.bibliothek.kit.edu/registration/) auennut

### Viikolla 16 tehty

#### Lari

  * Raporttien laadintaa/korjailua Lappiin ja Vaaraan
  * Lyngsoe-automaatin varauksen perumistoiminnon tutkimista.

  Tiketit

  * [Bug 39142 - Add debug permission to allow user to toggle JS and CSS customizations on/off](https://github.com/KohaSuomi/Bugiton/issues/57) https://github.com/KohaSuomi/Bugiton/issues/57
    [10.4.] Lisätty tuotantoon versionvaihdossa. Yhteisötiketin tila: Pushed to main for 26.05 Needs documenting.

  * [action_logs ja statistics taulujen pudotus seuraavien arkistointiajojen yhteydessä](https://github.com/KohaSuomi/koha-suomi-utility/issues/87) https://github.com/KohaSuomi/koha-suomi-utility/issues/87
    [15.4.] Action_logs- ja statistics-taulut pudotetaan aina ajon yhteydessä. Käytössä tuotannoissa.

  * [Itsepalvelulainaus: Asiakasnäkymään kirjautuminen ei pysy aktiivisena](https://github.com/KohaSuomi/Koha/issues/1764) https://github.com/KohaSuomi/Koha/issues/1764
    [15.4.] Suljen tiketin, sillä lisäongelmista ei ole raportoitu. Viimeisin muutos: https://github.com/KohaSuomi/Koha-25x/commit/cbd8a7499cc1a5e58efddae04aa40db28c6783c3 ks-0000-KohaSuomi-global-branchissa.

  * [Varauksen noutomuistutusilmoituksille sallittavat viestienvälitystavat](https://github.com/KohaSuomi/Koha/issues/2190) https://github.com/KohaSuomi/Koha/issues/2190
    [15.4.]  > [@lmstrand](https://github.com/lmstrand) Kyyti: varauksen noutomuistutuksen tilan selvittelyä: Testille on ajettu "takes_days"-arvo ykköseksi message_attributes-tauluun ja siksi "päivää ennen"-valinta näkyy. Viestiasetusten muutospyynnöt eivät kuulemma ole mennet läpi Kohaan tuotannossa, ennenkuin elementit on piilotettu Finnassa.

  * [Niteiden muokkaus eräajossa: Signum ei muodostu klikatessa kolmea pistettä.](https://github.com/KohaSuomi/Koha/issues/585) https://github.com/KohaSuomi/Koha/issues/585

    [17.4.] Outissa testillä käytetään loc_084a_mainheading_signum_builder.pl-pluginia, eikä siihen ole tehty tiketin 1759 https://github.com/KohaSuomi/Koha/issues/1759 yhteisen uuden signum_builder_ks.pl muutoksia, jonka takia uudet signumbuilderin ominaisuudet eivät toimineet Outissa.

  * [Finna-aineistotyyppi äänikirja myös Kohan aineistotyypiksi/MTYPE:ksi](https://github.com/KohaSuomi/Koha/issues/750) https://github.com/KohaSuomi/Koha/issues/750
    [16.4.] Sovittiin kehittäjäpalaverissa, että Lappi, Lumme ja Helle ajetaan tuotantoon korjausajot.

    [17.4.] Kaikkiin kimppoihin on suoritettu aineistotyyppien korjausajot.
    
  * [SIP-sanoma 15 aiheuttaa AFError with transaction drop_hold: -virheen, kun varausta yrittää peruuttaa (sanomassa 15-)](https://github.com/KohaSuomi/Koha/issues/2264) https://github.com/KohaSuomi/Koha/issues/2264
    [16.4.] Korjaus lisätty ksdev/ks-0043-K23-15-SIP2-branchiin ja viety testeille. OUTIn SIP-palvelin on käynnistetty uudelleen.

  Kommitit

  * KohaSuomi/Koha-25x
    * `345bd4e` [16.4.] Bug 39204: Added ability to cancel item-level holds via SIP

#### Anneli
* Maanantaina oli Kohan ruotsinkielisten tekstien käännöspalaveri, jossa käymme pienellä ryhmällä läpi puuttuvia ruotsinkielisiä käännöksiä.
* Tiistaina kävimme Heikkisen Antin kanssa läpi 21.4.2026 pidettävän [kuvailukoulutuksen](https://github.com/KohaSuomi/Koha/discussions/2171) materiaalin ja teimme lisäyksiä ja mietimme esimerkkejä koulutusta varten.
* Loin Vaskin Annille uuden sivupohjan Noutohylly-toiminnon käyttöönotto-ohjeita varten.
* Hellestä Kati huomasi, että jos tiedonhaun tuloksissa vaihtaa yläreunasta kirjautumiskirjastoa, tehdään haku uudelleen virheellisellä merkistökoodauksella. Esim. Rämö haetaan muodossa 'rÃ¤mÃ¶', jolloin hakutulos on väärä. Testasin tätä sandboxissa versiossa 25.11 ja ongelma toistui myös siellä, joten pyysin Katia tekemään tiketin suoraan yhteisön Bugzillaan.
* Katsoimme Pasin kanssa Tietuenäyttöjen mukautuksia varten tekoälyn avulla tekemiäni Template Toolkit -koodeja ja sovimme, että Pasi optimoi ne toimimaan paremmin. Sovimme, että testaan muutokset sen jälkeen.
* Keräsin asiantuntijaryhmän ensi viikon kokousta varten aiheet ja lähetin [alustavan esityslistan](https://koha-suomi.fi/asiantuntijaryhma2026#esityslista-42026) kokouksen osallistujille.
* Osallistuin keskiviikkona Koha-Suomen kuvailuryhmän kokoukseen, jonka muistio tulee jonkin ajan kuluttua luettavaksi myös Koha-Suomen verkkosivuille [Muistiot-osioon](https://koha-suomi.fi/kuvailuryhma2026).
  * Kokouksessa tuli esille, että TäTistä tietueita poimittaessa Z39.50-haulla "tippuu" toisinaan 942$c-kenttä ja kuvailija joutuu valitsemaan sen uudelleen. Testailin ongelmaa kokouksen jälkeen, enkä ensin saanut toistettua sitä. Lopulta se onnistui siten, että TäTissä olevalla tietueella oli 942$6-kentässä tietoja, mutta ei 942$c-kentässä. Meillä on Tietueiden yhdistämissäännöissä 942-kentälle sääntö "Suojaa poistamiselta", joka ei suojele kenttää tietojen päivittämiseltä toiseksi. Ongelmatapauksissa TäTissä olevat tiedot korvasivat paikalliset tiedot, jolloin se näytti siltä kuin 942$c-kenttä olisi pudonnut. Testailujen perusteella ehdotin Heikkisen Antille, että muuttaisimme yhdistämissäännöksi 942-kentälle ainakin toistaiseksi "Suojaa", jolloin paikalliskannassa oleva tieto säilyy aina, mutta ei synny tupla-942-kenttiä. Kirjasin ongelmasta [tiketin #2261](https://github.com/KohaSuomi/Koha/issues/2261) ja lisäsin sen pääkäyttäjien viikon 17 esityslistalle, koska käytännössä pääkäyttäjien pitää tämä muutos tehdä.
* Lisäsin aktiivisten branchien listalle pallerot brancheille ksdev/ks-0234-bug-G984-overdue-fines-branchcode ja ksdev/ks-0250-G1642-undelete-records, koska ne on päässyt mukaan versioon 26.05 ja pystymme luopumaan omista versiostamme kyseisissä toiminnoissa.
* Tutkin Lapissa Saarenkylän kirjastossa ilmennyttä ongelmaa, jossa näennäisti noudettavat varaukset eivät olleet vanhentuneet. Tarkempi tutkiminen osoitti kuitenkin, että ongelma liittyi jotenkin eri yhteyksissä näkyviin erilaisiin viimeiseen noutopäivään. Asiakkaan noutoilmoituksessa ja lokeilla oli viimeinen noutopäivä 16.4.2026, kun varauksen väliin laitettavassa infokuitissa oli viimeinen noutopäivä 14.4.2026. Virkailija oli palauttanut niteet uudelleen 15.4.2026, jolloin oli tulostunut uudelleen infokuitti päivämäärälle 14.4.2026. Tässä yhteydessä myös lokille kirjautui, että viimeinen noutopäivä muuttui 16.4.2026 -> 14.4.2026. Tein Lapin testille testivarauksen ja jatkan ihmettelyjä maanantaina. [Lappi: Vanhentuneet varaukset eivät vanhentuneet #2263](https://github.com/KohaSuomi/Koha/issues/2263)
* Kävin läpi tikettejä ja ehdottelin valmiisiin tiketin sulkemista. Osan suljin suoraan, koska niissä oli jo aiemmin tuloksetta ehdotettu sulkemista.
* Kävin läpi testattavana olevat tiketit ja testasin ne, jotka pystyin testaamaan.

#### Johanna

* Bug 42395: Fix missing translations on load_patron_holds_table (Bug-42395)
* Bug 42343: Prevent holds JS error when no holds exist (Bug-42343)
* squash this (Bug-41869)
* Bug 41869: Change place_holds permission to /holds POST and PATCH
* Bug 21004: (follow-up) remove unused modordernotes file (Bug-21004-community)
* Bug 21004: Use modal to add and edit notes on receiving orders/shipments page
* Bug 35722: (follow-up) fix parameters on catalogue detail page (Bug-35722)
* Bug 35722: Create item transfer REST api
* [Merge branch 'development' of https://github.com/KohaSuomi/koha-suomi-utility into development](https://github.com/KohaSuomi/koha-suomi-utility/commit/7c8f9519a8a7365ea50b92686ad0d3281134f8e4) (development)
* [Add local git changes to the summary](https://github.com/KohaSuomi/koha-suomi-utility/commit/353b76f4215bd65f9e33c971a16f1ca1d848c894) (development)
* Fix LocalHoldsPriotiyMaxHolds (ks25/ksdev/ks-0274-on-0243-KOHA-1563-prioritize-holds, ks25dev/ks-0274-on-0243-KOHA-1563-prioritize-holds)
* [Fix LocalHoldsPriotiyMaxHolds](https://github.com/KohaSuomi/Koha-25x/commit/65115d84b443baf8cef45fa09815367b71ff4ed6) (ksdev/ks-0274-on-0243-KOHA-1563-prioritize-holds)
* [Remove console.log](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/0d5df12418ad16bc3e677a5314077a15808b5b79) (ks25)
* [Update tests](https://github.com/KohaSuomi/koha-plugin-ceepos-integration/commit/b53e74a5a9dbbcf9e34158689e83ea5968cf6492) (master)
* [KohaSuomi/Koha - Varausten priorisointi: LocalHoldsPriority-järjestelmäasetukseen lisäys, että priorisoidaan vain x ensimmäisen varauksen osalta](https://github.com/KohaSuomi/Koha/issues/2028);
Vastuutettu: johannaraisa.
Kommentti: Tähän on tuotu korjaus testeile. LocalHoldsPriorityMinItems ja LocalHoldsPriorityHoldsPerItemThreshold rikkoivat käsittelyn, neljä samaan paikkaan vaikuttavaa asetusta saattaa ylikirjoittaa toisensa.
* [KohaSuomi/Koha - Maksujen muodostus hidasta versionvaihdon jälkeen](https://github.com/KohaSuomi/Koha/issues/2233);
Kommentti: > Tuossa fines.pl skriptissä on `-m --maxdays: how many days back of overdues to process` vipu. Mietin, että eikös se maksimimäärä maksuja (9€) tule vastaan n. 30 päivässä. Tarvitseeko edes katsella vanhempia myöhässä olevia kuin sen maksimimäärän? Tätä voisi ehkä kokeilla testillä tuolla vivulla. Siihen voi tietenkin laittaa isomman luvun kuin tuo 30, ehkä se mikä on määritelty laskutusrajaksi.
Kommentti: Tuossa fines.pl skriptissä on `-m --maxdays: how many days back of overdues to process` vipu. Mietin, että eikös se maksimimäärä maksuja (9€) tule vastaan n. 30 päivässä. Tarvitseeko edes katsella vanhempia myöhässä olevia kuin sen maksimimäärän? Tätä voisi ehkä kokeilla testillä tuolla vivulla. Siihen voi tietenkin laittaa isomman luvun kuin tuo 30, ehkä se mikä on määritelty laskutusrajaksi.
* [KohaSuomi/Koha - Niteiden muokkauksessa muokattava rivi ei pysy enää keltaisena tallennuksen jälkeen](https://github.com/KohaSuomi/Koha/issues/2252);
Vastuutettu: johannaraisa.
Kommentti: Tähän on yhteisössä korjaus, https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=41170
Kommentti: Ei ole vielä tuotu 25.05 versioon, pitää kysyä saisiko 25.05 versioonkin.
* [KohaSuomi/Koha - Luvitetut tekstiviestien lähettäjänimet palvelimelle](https://github.com/KohaSuomi/Koha/issues/2262);
Tiketti avattu.
Vastuutettu: johannaraisa.

#### Pasi
* Kirkes: kaukolainamoduulin asetukset koha-conffiin, sekä testille että tuotantoon. https://github.com/KohaSuomi/Koha/issues/2260
* Perustiedot-näytön "Jatkaa julkaisua" (yms, kentät 78x) linkit. https://github.com/KohaSuomi/Koha/issues/532
* Signummuutos, Kirkes: lehtitilausten korjaus. https://github.com/KohaSuomi/Koha/issues/2043

#### Kodo
* [Koha#2253 Jaetun kuvailutietovarannon muodostaminen testeille](https://github.com/KohaSuomi/Koha/issues/2253);
Testikantojen bibliografinen data yhdistetty TäTi-testin biblio*\_k-tauluihin. Seuraavaksi temppisarakkeiden poisto, biblio-taulujen korvaus täti-testillä, kimppojen testien biblio-taulujen pudotus + näkymät testeille, testien niteiden, lainojen ja varausten päivittäminen mäppäystaulun perusteella, indeksointi.
* [Koha#2265 Vaara: Seutukirjaston toimittaja-asiakkuuksien yhdistäminen: fundit/budjetointi ja asiakasnumerot](https://github.com/KohaSuomi/Koha/issues/2265). Joensuun seutukirjastossa halutaan keskittää vastaanotto pääkirjastolle säilyttäen kuitenkin niteiden kotikirjastot. Ajatuksena on vähentää aineistontoimittajakohtaisia asiakkuuksia, jotta tilaukset yhdistyvät samoihin lähetyksiin ja laskuille. Yhtenä vaihtoehtona on, että kuntakohtaisia fundeja hallitaan Joensuun budjetin alla. Kohassa keskeistä on fundnumberin täsmääminen. Aineiston sijoitus määräytyy DeliverToLocation ja DestinationLocation tagien perusteella, joten varmistettava että muutoksen jälkeen EDItX-sanomissa tagit tulevat halutusti. Odottaa jatkotoimenpiteiden selkiytymistä.
* [Koha#2236 Ajastetut ajot testeillä](https://github.com/KohaSuomi/Koha/issues/2236); Huomio vaski-testin fines.pl -ajo kesti n. 10h. Linkitetty maksujen hidastumiseen (#2233) + tuotannon ajoaika tarkistettu, Vaski-tuotannon saman päivän maksuajo on kestänyt 25 minuuttia.
* [Koha#1829 EDItX RSA1 avainten vaihto](https://github.com/KohaSuomi/Koha/issues/1829); Muistutettu Kirjastopalvelua avaimen toimituksesta uudelleen. Tämä taitaa nyt olla viides kerta kun sieltä yritetään saada avainta.
* [koha-suomi-utility#115 BSD-nodejen käyttispäivitykset](https://github.com/KohaSuomi/koha-suomi-utility/issues/115);
Node-ongelma selvitetty; molemmille nodeille käyttispäivitykset, ja Tatu päivitetty FreeBSD 14.4:ään.
* [koha-suomi-utility#116 Patun RAID-kontrollerin firmware](https://github.com/KohaSuomi/koha-suomi-utility/issues/116);
Kartoitettu laitteisto/RAID-ohjain ja tarvittava firmware. Ohjeistettu operaattorille firmware-päivitys Lenovon UpdateXpressillä. Kysymyksessä voi myös olla laitevika, jolloin firmware-päivitys ei ratkaise ongelmaa. Siinä tapauksessa täytyy selvittää saadaanko varaosia ja onko korjaus järkevää.
* [koha-suomi-utility#117 Backup health check on hidastunut tiered backuppeihin siirtymisen jälkeen](https://github.com/KohaSuomi/koha-suomi-utility/issues/117); Datan keräämisen hidastuminen on aiheuttanut nodeille kirjautumiseen huomattavan viiveen. Korjattu lisäämällä välimuistitus. Raportointi rajattu pelkkiin virheisiin. Seurataan ja suljetaan myöhemmin.

## Viikko 16
Aika: Ma 13.4.2026<br />
Läsnä: Ari, Johanna, Anneli, Pasi, Kodo

### Vastuuttomat tiketit
* [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

### Muut asiat

* Viikon 16 päivitys

### Viikolla 15 tehty

#### Emmi
* [Varausten vienti raportilta erämuokkaukseen epäonnistuu isoilla määrillä](https://github.com/KohaSuomi/Koha/issues/1980)
Yhteisöstä löytyi korjaus, jolla raporteilta on mahdollista viedä 400 kappaletta varauksia varaustyökaluun. Korjaus tuotu testattavaksi testeille.
-> Tätä testattiin testeillä ja lopputulema oli, että tilanne on palannut takaisin versionvaihtoa edeltäneeseen tilanteeseen. Eli varauksia voi viedä 200 kappaletta, isommat määrät aiheuttavat joko Bad Gateway tai Request-URI Too Long virheen. Isompien määrien viemisen toimimaan saaminen vaatisi luultavasti isompaa remonttia Kohan datatables-elementtien ja holds endpointin toimintaan.
* [Vaski: IntranetUserJS päivitys](https://github.com/KohaSuomi/Koha/issues/2245); Päivitys tehty yhdessä Vaskin pääkäyttäjän kanssa.
* [Lastu: Laskut jääneet lähtemättä](https://github.com/KohaSuomi/Koha/issues/2250); Selvitetty onko laskutusajossa tapahtunut meidän päässämme virhettä. Selvisi, että laskut ovat lähteneet meiltä onnistuneesti, mutta ne ovat jääneet lähtemättä vastaanottavalta palvelimelta eteenpäin. Kehotettu olemaan yhtydessä vastaanottajaan. 
* [Tilauksen peruutus ei varoita että niteet poistetaan](https://github.com/KohaSuomi/Koha/issues/2050); Yhteisöön viety ehdotus, jossa tilauksen perumisen yhteydessä ilmoitetaan, että tilaukseen liittyvät niteet poistetaan. Tätä ei ole vielä tuotu meille testattavaksi, odotetaan yhteisön kommentteja asiasta.
* Edellisen yhteydessä huomattu, että tilauksen epäonnistunut poisto voi aiheuttaa tuplaid:n items- ja deleteditems-tauluhin. Havainto raportoitu yhteisöön tiketissä [Bug 42303](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=42303) - Duplicate itemnumber in items and deleteditems table when order cancel fails

#### Lari

  Tiketit

  * [Lappi: Listaus sip-palvelimelle yhteyden saavista automaateista](https://github.com/KohaSuomi/Koha/issues/2234) https://github.com/KohaSuomi/Koha/issues/2234
    [7.4.] Lähetin @LeenaKinnunen Matrixiin tämän päivän ja viime viikon ajalta lokeilta kerätyt tunnukset, joilta on tullut liikennettä.

  * [99-sanomien käsittely SIP-palvelimen ohi](https://github.com/KohaSuomi/Koha-25x/issues/192) https://github.com/KohaSuomi/Koha-25x/issues/192
    [8.4.] Rajapinnassa luotujen SIP-vastausten generoimisen jälkeen on nyt lisätty #remove carriage return/line feed from response ennen kuin muuttujat välitetään XML:n muodostajalle. Muutos testeillä testattavana.

  * [Varaukset-sivulle sivutus](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/39) https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/39
    [9.4.] Koha tukee sivutusta ja api-kyselyjä voi muutenkin optimoida.  esim: GET /api/v1/patrons/123/holds?page=1&per_page=20  vastauksessa Headerinä kokonaismäärä: X-Total-Count: 105 X-Base-Total-Count: 105  Dataa voi myös yhdistellä kyselyjen optimoimiseksi: GET /api/v1/patrons/123/holds?per_page=-1 x-koha-embed: biblio,item,pickup_library. Laitoin Finna-kehittäjälle nämä optimointiehdotukset varausten hakemiseen Kohasta. 

  * [Maksujen muodostus hidasta versionvaihdon jälkeen](https://github.com/KohaSuomi/Koha/issues/2233) https://github.com/KohaSuomi/Koha/issues/2233
    [9.4.] Tiketti yhteisössä: https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=42297

  * [Bug 39142 - Add debug permission to allow user to toggle JS and CSS customizations on/off](https://github.com/KohaSuomi/Bugiton/issues/57) https://github.com/KohaSuomi/Bugiton/issues/57
    [10.4.] Lisätty tuotantoon versionvaihdossa. Yhteisötiketin tila: Pushed to main for 26.05 Needs documenting.

  * AI-työkalujen opiskelua
  * Vaarassa havaitun raporttiesimerkin toiminnan muutoksen tutkintaa. Pyydetty tekemään pääkäyttäjän kautta tiketti.

#### Kodo

* [Kuukausihuollossa tarvittavat päivitykset kaikille palvelinnodeille ja koha-kontainereihin.](https://github.com/KohaSuomi/Koha/discussions/2240) Huollon jälkeen havaittu DB2 muistikamman vioittuminen, josta syystä kaksi muistikampaa pois käytöstä tilasto/raporttipalvelimella.
* [INNODB buffer pool muutos tietokantapalvelimella](https://github.com/KohaSuomi/Koha/issues/2249);
INNODB buffer pool muutos DB2:lla vioittuneen muistikamman vuoksi. Tiketti jätetty odottaa-tilaan muistikamman vaihtoa ja asetuksen palauttamista varten. Seuraavaksi muistikamman vaihto kuukausihuollossa ja asetuksen palautus.
* [Muistioiden generointi ja muistioformaatti](https://github.com/KohaSuomi/Koha/issues/2246);
uuteen muistioformaattiin pyydetty kommentteja pääkäyttäjiltä Matrixissa; lisätty muistio-linkki ja todettu että uusi formaatti käytössä viikosta 14 alkaen. Lisätty muistiodokumentin alkuun huomautus että muistioiden laadinnassa voidaan jatkossa hyödyntää tekoälyä. Seuraavaksi kerätään palaute ja vakiinnutetaan formaatti sekä generointiskriptin-ajo.
* [Yli 20 merkkiset viivakoodit testeillä.](https://github.com/KohaSuomi/Koha/issues/2243);
ylipitkiä tunnuksia sisältävät niteet siirretty testeillä tauluun `items_overlong_barcodes` (määrät vaihtelevat, Vaskissa reilut 1000).
* [Sotuteekin lukituksen poisto](https://github.com/KohaSuomi/Koha/issues/2244); lukitus purettu ja tiketti suljettu.
* [Tilastoviiveen raportointi](https://github.com/KohaSuomi/Koha/issues/2148); todettu toimivaksi ja tiketti suljettu.
* [Tietokantadumppien jakaminen](https://github.com/KohaSuomi/Koha/issues/2081); tarkennettu tason 0 dumpin järjestys (dumpataan viimeisenä, palautetaan ensimmäisenä) ja todettu tuotantoon viedyksi ja toimivaksi; tiketti suljettu.
Seuraavaksi varmistusjärjestelmän ja palautusten dokumentointi, työn alla, mutta tiketöitävä.
* [Ajastetut ajot testeillä](https://github.com/KohaSuomi/Koha/issues/2236); RunTestCronjobs-järjestelmäasetus + testeille mukautetut crontabit otettu käyttöön kaikkien kimppojen testeissä. Ohjeistettu käyttö (Local Use → RunTestCronjobs). Commit [koha-suomi-utility commit 76eb038 (development)](https://github.com/KohaSuomi/koha-suomi-utility/commit/76eb0383978bda90012a28b23c30a4aad7b08b4f).
* [Maksujen muodostus hidasta versionvaihdon jälkeen](https://github.com/KohaSuomi/Koha/issues/2233);
kuvattu syyhypoteesi (uudet joinit/sarakkeet + kuorma puoliltaöin) ja luvattu tuotantotietokantoihin uusi indeksi laskennan nopeuttamiseksi. Paikallisia koodimuutoksia ei tehdä ja verkkokirjaston maksukatkon pidentämistä suositeltu.
Seuraavaksi indeksin lisäys tuotantoon ja vaikutuksen seuranta (maksujen laskennan kesto / kuorma). Lari avannut tiketin maksujen laskennan koodin tehostamisesta yhteisöön.
* [Vaski: Raporttien ajaminen Raportterin kautta epäonnistunut](https://github.com/KohaSuomi/Koha/issues/2232);
esitetty mahdolliseksi syyksi raporttipalvelimen muistiongelma tai muut yölliset “glitchit” (logrotaten jälkeinen starmanin uudelleenkäynnistys). INNODB buffer poolin muutos vakauttanee tilanteen kunnes palvelimen vioittunut muisti on korjattu.
Seuraavaksi seuranta muistikamman vaihdon jälkeen ja virheiden toistumisen tarkkailu.
* [Koha antoi virheen 500, kun asiakkaalle koitti lainata toiselle asiakkaalle varatun/laiantun kirjan](https://github.com/KohaSuomi/Koha/issues/2251); siirretty Koha-tietovarantoon.
Seuraavaksi vastuutus ja korjauksen suunnittelu Koha-tietovarannossa.
* [Niteiden muokkauksessa muokattava rivi ei pysy enää keltaisena tallennuksen jälkeen](https://github.com/KohaSuomi/Koha/issues/2252); siirretty Koha-tietovarantoon (versiopäivitys tehty).
Seuraavaksi vastuutus ja korjauksen suunnittelu Koha-tietovarannossa.
* [Kaukolainapyynnöt - asiakkaan nimen piilotus](https://github.com/KohaSuomi/Koha/issues/2255);
tiputettu “Tehtävä”-status pois. Seuraavaksi sovitaan toteutus ja vastuutus viikkopalaverissa.
* [Tunnusten automaattihallinnan parannukset](https://github.com/KohaSuomi/koha-suomi-utility/issues/111);
suunniteltu tietoturvaan liittyviä parannuksia käyttäjätunnusten automaattiseen käsittelyyyn.
Seuraavaksi tiketti käytetään asiantuntijaryhmässä, jossa päätetään parametroinnista. Sen jälkeen muutoksen toteutus.
* [Testien lokirotaation service-check](https://github.com/KohaSuomi/koha-suomi-utility/issues/112);
poistettu käytöstä ja tiketti suljettu.
* [Cronjobtriggerit](https://github.com/KohaSuomi/koha-suomi-utility/issues/113);
Cronjobtriggerien yhdistämisen suunnittelu ja toimita triggerin kanssa jatkossa.
Seuraavaksi triggerien yhdistäminen ja testien TRIGGER-muuttujien päivitys. Samalla korjataan myös utility#103.
* [Hostkey sähköpostihälyjen poistaminen käytöstä](https://github.com/KohaSuomi/koha-suomi-utility/issues/114);
hostkey-hälytykset poistettu käytöstä (valtaosin epäajantaisia ja tarpeettomia) ja vanhat hälyt siivottu admin-laatikosta; tiketti suljettu.
* [zebradb-konfigeissa roikkuu viittauksia jaettuun /home/koha/koha-dev:iin](https://github.com/KohaSuomi/koha-suomi-utility/issues/108); viittaukset vaihdettava vielä nexteille; linkitetty next-roolin päivitykseen.
Seuraavaksi vaihto nexteille ja varmistus ettei /home/koha/koha-dev -riippuvuuksia jää.
* [/home/koha hakemistossa perl5 modulihakemisto](https://github.com/KohaSuomi/koha-suomi-utility/issues/109);
OAI-testauksessa testeillä virhe `Can't call method "processing_instruction" ... HTTP/OAI/Response.pm line 115`.
Seuraavaksi virheen syyn selvitys (HTTP::OAI / ympäristö / data) ja korjaus; OAI-uusintatesti.
* [Jaetun kuvailutietovarannon muodostaminen testeille](https://github.com/KohaSuomi/Koha/issues/2253);
TäTi-testille yhdistetään testi-Kohien kuvailutietueet yhteen tietokantaan ja jaetaan ne näkyminä kaikkiin testi-installaatioihin (valmistautuminen jaettuun kuvailutietovarantoon).
Seuraavaksi tietueiden alustava yhdistely ja testaukset testi-kannoissa.
* [Pseudonymisoinnissa huomioitavaksi etunimettömät asiakastyypit](https://github.com/KohaSuomi/Koha/issues/2157);
siivottu testeiltä preferred_name -jäämät asiakastyypeiltä `API`, `AUTOM`, `KAUKOLAINA` ja `YHTEISO`.
* [EDItX RSA1 avainten vaihto](https://github.com/KohaSuomi/Koha/issues/1829);
odotetaan edelleen Kirjastopalvelun avaintoimitusta: avain toimitettiin Google Drivessä (vaatii Google-kirjautumisen), pyydetty toimittamaan julkinen avain sähköpostilla.

#### Johanna

* [KPODUE-22: Replace buyer_name with one on the database](https://github.com/KohaSuomi/koha-plugin-overdue-tool/commit/fb81af8) (koha-plugin-overdue-tool - master)
* [Add week flag and improve the output](https://github.com/KohaSuomi/koha-suomi-utility/commit/8f6ec93) (koha-suomi-utility - development, master)
* [Update kohasuomi2026.md](https://github.com/KohaSuomi/kohasuomi.github.io/commit/cc0451f) (kohasuomi.github.io - master)
* [Add custom class to _pages files](https://github.com/KohaSuomi/kohasuomi.github.io/commit/fc7730f) (kohasuomi.github.io - master)
* [Adjust the css for only _pages files](https://github.com/KohaSuomi/kohasuomi.github.io/commit/e58308e) (kohasuomi.github.io - master)
* [Add sticky sidebar](https://github.com/KohaSuomi/kohasuomi.github.io/commit/14c42c0) (kohasuomi.github.io - master)
* [Adjust the width of the page](https://github.com/KohaSuomi/kohasuomi.github.io/commit/54a616e) (kohasuomi.github.io - master)
* [Add custom css for page width](https://github.com/KohaSuomi/kohasuomi.github.io/commit/c047cb7) (kohasuomi.github.io - master)
* [Update kohasuomi2026.md](https://github.com/KohaSuomi/kohasuomi.github.io/commit/8de2f8f) (kohasuomi.github.io - master)
* [Remove single from template](https://github.com/KohaSuomi/kohasuomi.github.io/commit/437d663) (kohasuomi.github.io - master)
* [KohaSuomi/Koha - Vaski: Raporttien ajaminen Raportterin kautta epäonnistunut](https://github.com/KohaSuomi/Koha/issues/2232);
Vastuutettu: johannaraisa.
Kommentti: Kyllä ne Emailerin kutsut näkyy tulevan klo 2 yöllä. Ei tässä voi kuin seurata ja ehkä tuo muistikamman vaihto auttaa asiaa.
Kommentti: Vaskissa plack on käynnistynyt 8.4. uudestaan klo 0.12, joten en usko sen tuohon vaikuttavan.
* [KohaSuomi/Koha - Muistioiden generointi ja muistioformaatti](https://github.com/KohaSuomi/Koha/issues/2246);
Kommentti: Parantelin "github-weekly-summary"-skriptiä, nyt sen pitäisi tehdä nuo oikeassa muodossa kun ajaa note-vivulla. Lisäksi kävin lisäämässä verkkosivulle tyylin joka leventää noiden muistioiden leveyttä. Aika kapea oli tällaisella isolla näytöllä katsella.
* [KohaSuomi/Koha - Pelkillä place_holds + view_borrower_infos_from_any_libraries -käyttöoikeuksilla ei voi tehdä uusia varauksia](https://github.com/KohaSuomi/Koha/issues/2247);
Vastuutettu: johannaraisa.
Kommentti: Puuttuuko käyttäjältä list_borrowers, tuossa etsitään ja listataan asiakkaita, joten se pitäisi olla jos haluaa sellaista tehdä?
* [KohaSuomi/Koha - Tietueiden siirto Melindaan takkuaa](https://github.com/KohaSuomi/Koha/issues/2256);
Vastuutettu: johannaraisa.
Kommentti: Tätä selvitellään Kansalliskirjaston kanssa, vaikuttaa siltä ettei heidän REST käsittele tietueita tarpeeksi nopeasti ja siksi tulee timeout-virhettä.
* [KohaSuomi/koha-plugin-overdue-tool - Sukunimi erottumaan selvästi etunimistä](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/22);
Vastuutettu: johannaraisa.
Kommentti: Varmaan nexteillä yhdistelty sellainen versio mihin on jäänyt tuota koodia. Lisäsin nyt testeille version missä pitäis nuo sukunimet näkyä isolla.
* [KohaSuomi/koha-plugin-record-manager - Tee käyttöliittymä](https://github.com/KohaSuomi/koha-plugin-record-manager/issues/1);
Tiketti suljettu.
* [KohaSuomi/koha-plugin-record-manager - Käyttöliittymään sivutus](https://github.com/KohaSuomi/koha-plugin-record-manager/issues/2);
Tiketti avattu.
Vastuutettu: johannaraisa.
* [KohaSuomi/koha-plugin-record-manager - Käyttöliittymässä oleva haku toimimaan APIn kautta.](https://github.com/KohaSuomi/koha-plugin-record-manager/issues/3);
Tiketti avattu.
Vastuutettu: johannaraisa.

#### Pasi
* Signum-muutoksen valmistelua Outiin, testiajo
* Tietuenäytön/hakunäytön muokkausasetusten parantelua


## Viikko 15

Maanantain viikkopalaveria ei pidetty pääsiäisen vuoksi. Vastuuttomat tiketit vastuutetaan ensi viikon palaverissa.

### Viikolla 14 tehty

#### Kodo
* [Ajastetut ajot testeillä](https://github.com/KohaSuomi/Koha/issues/2236);
testicronjobien perussetti listattu (OUTI-test), `update-holds-to-pull`-kuormariski huomioitu, syspref-ohjaus (**RunTestCronjobs**) toteutettu testiajojen määräaikaiseen päälle/pois-kytkentään.
* [Lappi: Omatoimikirjaston käyttökiellon asettaminen asiakkaalle](https://github.com/KohaSuomi/Koha/issues/2239);
estot asetettu.
* [Lappi: Listaus sip-palvelimelle yhteyden saavista automaateista](https://github.com/KohaSuomi/Koha/issues/2234);
kesken. SIP-palvelimelle väärällä RO-tunnuksella yhteyttä ottavat Lapin automaatit. Pyydetty SIP-palvelimelta lista yhteyttä ottavista automaateista rajauksen tekemiseksi.
Seuraavaksi SIP-lista ulos ja tunnusten/salasanojen tarkistus niille automaateille, jotka ottavat yhteyttä väärällä RO-tunnuksella.
* [Vaara: Ceepos kassajärjestelmän muutostyöt](https://github.com/KohaSuomi/Koha/issues/2235);
kesken, vanha IPsec-tunneli purettu, uusi liikennöinti kesken. Koha-päähän tarvitaan ceepos-yhteysosoitteen muutos + tarkistuspalaveri + testaus, eteneminen Meita/CPU:n aikataululla.
Seuraavaksi ceepos-yhteysosoitteen muutos Kohaan + yhteistestaus Meita/CPU:n kanssa (palaveri + testit).
* [/var/etc/hakemiston siivous](https://github.com/KohaSuomi/Koha-25x/issues/169);
siivottu, vanhat tiedostot siirretty `/var/etc/koha/old`-hakemistoon, jatkotoimet (sms_send + koha-conf → utility #105–#108); tiketti avattu takaisin kunnes liittyvät tiketit hoidettu.
Seuraavaksi utility-tikettien #105–#108 läpivienti ja tämän sulkeminen niiden jälkeen.
* [zebradb-konfigeissa roikkuu viittauksia jaettuun /home/koha/koha-dev:iin](https://github.com/KohaSuomi/koha-suomi-utility/issues/108);
viittaukset siivottu, konffit vaihdettu prod- ja test-roolien kontteihin.
* [Vanhat easticsearch-dumpit ja -hakemistot pois](https://github.com/KohaSuomi/koha-suomi-utility/issues/101);
indeksien dumppaus ja synkkaus siirretty versiopäivityksessä Elmalle; vanhat dumpit ja `elasticsearch.ondisk`-hakemistot poistettu tuotannoista ja varmistuksista. (tausta: [Elma tuotantoon](https://github.com/KohaSuomi/koha-suomi-utility/issues/30))
* [sms_send driverin siirto /var/koha/etc:stä tarkoituksenmukaisempaan paikkaan](https://github.com/KohaSuomi/koha-suomi-utility/issues/105);
sms_send todettu YAML-konffiksi (ei driveri) → jätetty etc:iin.
* [/home/koha hakemistossa perl5 modulihakemisto](https://github.com/KohaSuomi/koha-suomi-utility/issues/109);
korjaus tehty testeillä, `koha_perl_deps.pl` OK, OAI testaus vielä tekemättä.
* [MariaDB systemd service unitin korjaus](https://github.com/KohaSuomi/koha-suomi-utility/issues/70);
todettu, ettei palvelu käynnisty aina automaattisesti.
* [Vanhat tietokantadumpit pois](https://github.com/KohaSuomi/koha-suomi-utility/issues/104);
kesken, tiered dumppeihin siirtymisen jälkeen vanhat tietokantadumpit poistettava varmistusjärjestelmästä manuaalisesti, poistossa huomioitava säilytysajat (erityisesti LTS).
Seuraavana poistojen ajosuunnitelma (mitä poistetaan/mistä) + toteutus säilytysaikojen puitteissa + kuittaus tikettiin.
* [next-roolin konttipohja pitää uusia](https://github.com/KohaSuomi/koha-suomi-utility/issues/110);
kesken, next-roolin konttipohja päivitettävä vastaamaan maaliskuu 2026 -versionvaihdon jälkeisiä tuotantoja ennen seuraavaa versiopäivitystä.
Seuraavana erot tuotanto ↔ next -konttipohja kartoitetaan ja konttipohja päivitetään vastaamaan nykyisiä tuotantoja.
* [LimitRequestBody-asetuksen muuttaminen palvelimella](https://github.com/KohaSuomi/koha-suomi-utility/issues/69);
kesken, Apachen `LimitRequestBody` ei rajoittava (apache “unlimited”). Myös HAProxyyn suunnitellut `tune.bufsize`/`tune.maxrewrite`-muutokset päätetty jättää tekemättä, koska ongelma muuttui Koha 3/2026 -versiossa ja epäonnistuu myös pienillä määrillä (vika ei todennäköisesti HAProxyssä).
Seuraavana toisto pienellä aineistolla + lokien keruu (Koha + LB/HAProxy) ja rajaus, onko kyse request-koosta vai sovellus-/backend-ongelmasta.

#### Johanna
* [Fix subroutine warning](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/40ada99) (koha-plugin-broadcast-biblios - master)
* [Revert "Find active record with 035z"](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/a962e9c) (koha-plugin-broadcast-biblios - ks25)
* [Fix subroutine warning](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/625fff6) (koha-plugin-broadcast-biblios - ks25)
* [Revert "Limit 035z from search"](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/736cb20) (koha-plugin-broadcast-biblios - ks25)
* [Revert "Add system-control-number-cancelled to queryparser"](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/cc83c81) (koha-plugin-broadcast-biblios - ks25)
* [Rename script](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/3e8add5) (koha-plugin-broadcast-biblios - master)
* [Merge branch 'ks25' of https://github.com/KohaSuomi/koha-plugin-broadcast-biblios into ks25](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/0b1ad54) (koha-plugin-broadcast-biblios - ks25)
* [Rename script](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/e1ebbf3) (koha-plugin-broadcast-biblios - ks25)
* [Rollback for parameter push](https://github.com/KohaSuomi/koha-plugin-report-services/commit/bce6a84) (koha-plugin-report-services - ks25)
* [KOHA-2232: Improve parameter input and error logging](https://github.com/KohaSuomi/koha-plugin-report-services/commit/12e2d3b) (koha-plugin-report-services - master)
* [KOHA-2232: Improve parameter input and error logging](https://github.com/KohaSuomi/koha-plugin-report-services/commit/3b36d8f) (koha-plugin-report-services - ks25)
* [Create github-weekly-summary.pl and README](https://github.com/KohaSuomi/koha-suomi-utility/commit/c6a2a35) (koha-suomi-utility - development, master)
* [Rename format_markdown as format_standard and update README](https://github.com/KohaSuomi/koha-suomi-utility/commit/37ebc86) (koha-suomi-utility - development, master)
* [Create just-for-fun and add educational scripts](https://github.com/KohaSuomi/koha-suomi-utility/commit/d0833af) (koha-suomi-utility - development, master)
* [Rename username variable example for weekly summary](https://github.com/KohaSuomi/koha-suomi-utility/commit/8766a65) (koha-suomi-utility - development, master)
* [Fetch commits across all branches not just default](https://github.com/KohaSuomi/koha-suomi-utility/commit/1cb7d9d) (koha-suomi-utility - development, master)
* [Update kohasuomi2026.md with recent changes](https://github.com/KohaSuomi/kohasuomi.github.io/commit/423bde7) (kohasuomi.github.io - master)
* [Change text in note](https://github.com/KohaSuomi/kohasuomi.github.io/commit/deac7eb) (kohasuomi.github.io - master)
* [Update kohasuomi2026.md with notes](https://github.com/KohaSuomi/kohasuomi.github.io/commit/d927a5d) (kohasuomi.github.io - master)
* [Document updates on Koha system issues and fixes](https://github.com/KohaSuomi/kohasuomi.github.io/commit/649c7b1) (kohasuomi.github.io - master)
* [Fix formatting](https://github.com/KohaSuomi/kohasuomi.github.io/commit/8f3402a) (kohasuomi.github.io - master)
* [Fix punctuation in issue responsibility note](https://github.com/KohaSuomi/kohasuomi.github.io/commit/57b1cea) (kohasuomi.github.io - master)
* [KohaSuomi/Koha - Tietueen Varaukset-välilehdellä englannikielisiä termejä ](https://github.com/KohaSuomi/Koha/issues/1492);
Vastuutettu: johannaraisa.
Kommentti: Tähän on tägit testeillä, mutta taitaa vaatia kielitiedostojen tekemisen.
* [KohaSuomi/Koha - Tietuesiirtäjä lisäilee satunnaisesti ylimääräisiä 942c-kenttiä TäTissä](https://github.com/KohaSuomi/Koha/issues/2229);
Vastuutettu: johannaraisa.
* [KohaSuomi/Koha - Vaski: Raporttien ajaminen Raportterin kautta epäonnistunut](https://github.com/KohaSuomi/Koha/issues/2232);
Vastuutettu: johannaraisa.
Kommentti: Olen parannellut sitä muuttujien ja virheiden käsittelyä, saa ainakin lokittamaan paremmin. Testasin jo testillä, sitä ei oikein pysty muut testaamaan, joten laitan sen tuonne tuotantoon ja katsellaan mitä siellä näkyy.
Kommentti: Toinen mitä mietin, että voisiko olla niin, että se raportti ei palauta mitään, ei siis ole dataa sille päivälle tarjolla ja antaa virheellisesti 500 virheen.
* [KohaSuomi/Koha - Käyttöoikeuksia voi asettaa vain tietyille asiakastyypeille](https://github.com/KohaSuomi/Koha/issues/2237);
Tiketti avattu.
* [KohaSuomi/Koha - Rinnakkaisvaraus - Bug 15516 - Allow to place a hold on first available item from a group of titles](https://github.com/KohaSuomi/Koha/issues/2241);
Vastuutettu: johannaraisa.
Kommentti: Siirsin tämän tiketin Koha-repoon, ei enää liity versiovaihtoon.
* [KohaSuomi/Koha-25x - Vaski: "Print slip and confirm" -painike ei toimi kun varauksen palauttaa ensimmäisen kerran](https://github.com/KohaSuomi/Koha-25x/issues/244);
Vastuutettu: johannaraisa.
Kommentti: Tämä on nyt tuotannossa.
* [KohaSuomi/Koha-25x - Varauksen palautuksesta kaksi erilaista varausmodaalia](https://github.com/KohaSuomi/Koha-25x/issues/245);
Vastuutettu: johannaraisa.
Kommentti: Tässä ei taida olla muuta kuin tuo, että se modaali näkyy englanniksi. Käännösongelmasta taisi olla toinen tiketti, joten voisiko tämän sulkea ja käsitellä asiaa siellä?
* [KohaSuomi/Koha-25x - Tietuesiirtäjä: Muutokset -popparin kenttien tiedot yhdelle riville](https://github.com/KohaSuomi/Koha-25x/issues/247);
Vastuutettu: johannaraisa.
Kommentti: Tämä on tuotannossa.
* [KohaSuomi/koha-plugin-broadcast-biblios - OAI-setin siivousskripti](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/19);
Vastuutettu: johannaraisa, Anknite-cpu.
Kommentti: Tämä on ajettu Tätissä, vaatii vielä tarkistamisen ettei uusia synny ennen kuin suljen tiketin.
* [KohaSuomi/koha-plugin-report-services - Oma lokitiedosto raportterirajapintaan](https://github.com/KohaSuomi/koha-plugin-report-services/issues/13);
Tiketti suljettu.
* [KohaSuomi/koha-plugin-visual-label-tool - Virhekäsittelyt eivät toimi oikein](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/issues/11);
Vastuutettu: johannaraisa.
Kommentti: Käännösten lisääminen liitännäiseen rikkoi muokkauksessa virheviestien näkymisen. Samalla parantelin virheviestejä, jotta niistä ymmärtäisi paremmin mikä on vikana.


## Viikko 14

Aika: Ma 30.3.2026<br />
Läsnä: Ari, Lari, Johanna, Anneli, Emmi, Pasi, Kodo

### Vastuuttomat tiketit
* [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

### Muut asiat
* Asioiden kirjaaminen palaverimuistioon on jäänyt retuperälle, kuinka tätä tilannetta voitaisiin parantaa ja missä laajuudessa asioita on hyvä kirjata? Nyt tehtyjen muutosten seuraaminen on hankalaa.
  * Kehittäjät kirjaavat tähän muistioon muiden tiedoksi asiat koko viikon ajalta.
* Päivitys ajetaan maanantai-iltana

### Viikolla 13 tehty

#### Anneli
* Tietuenäyttöjen mukautuksista raportoitiin ongelmia kentän 020q-osalta. Ongelma johtui siitä, että Template Toolkit -sääntö ei huomioinut sitä, että q-osakenttä voi toistua. Laitettu testattavaksi toistot huomioiva versio
* Kuvailusääntöihin on tehty muutos, jossa 800t-osakenttään aletaan kirjaamaan sarjan nimekkeen perään tieto "(teksti : nide)". Tämä rikkoo Sarja-tiedon hakulinkin, koska sarjaa haetaan t-kentän sisällön mukaisesti, esim. Myrskylän retket (teksti : nide). Kaikissa tietueissa ei kuitenkaan ole tuota uuden kuvailusäännön mukaista lisätietoa, joten ne eivät osu hakuun. Koitin ratkoa ongelmaa lisäämällä tietuenäyttöjen mukautus -työkalulla uuden Sarja-otsikon, joka tekee hakulinkin ilman tuota (teksti : nide) -lisäystä. Sain sen toimimaan, mutta huomasin sen jälkeen, että kuvailusääntöjen mukaan 800t-kenttään voidaan lisätä tietoja myös vähän toisessa muodossa, jos kyseessä on erikielisiä teoksia, esim. (teksti: nide : ruotsi). Tämä tieto tarkoittaa, että nykyinen regex ei toimi. Lisäksi ilmeisesti sarjatietoa haetaan myös 490-kentästä niissä tapauksissa, että sarjaan ei liity tekijää, eli silloin ei tehdä ollenkaan 800-kentän kirjausta. Tämä vaatii siis vielä pohdintaa.
* Eräpäivän siirto -työkalussa on ongelmana, että se näyttää esikatselussa uuden eräpäivän vain noin puolelle valituista. Eräpäivä kyllä muuttuu kaikille, vaikka tieto puuttuukin esikatselusta.
* Oulussa oli ongelma maksujen viennissä Ceepos-kassaan. Se epäonnistui välillä. Syyksi paljastui asiakkaan Lainaus-sivulla oleva Huomioi-kentän Maksa kaikki maksut -nappi, joka vei sellaiseen näkymään, jossa maksujen vienti Ceepokseen ei onnistu, koska osoitteessa ei ole mukana yksittäisten maksujen accountline_id:t. Pikakorjauksena kielletty käyttää kyseistä nappia ja Lari tekee kestävämmän korjauksen suoraan Ceepos-liitännäiseen eli piilottaa kyseisen nappulan.
* Lastussa oli lähtenyt asiakkaalle palautuskehotus, jossa ei ollut item-tägin sisälle muodostunut teostietoja. Epäilin ensin, että asiakas on ehtinyt palauttaa niteen siinä välissä, kun viesti on luotu, mutta ei vielä lähetetty. Teokset oli kuitenkin palautettu vasta viestin lähetyksen jälkeen, joten tämä teoria ei pitänyt paikkansa. Tämä saattaa jäädä mysteeriksi, koska muita vastaavia tapauksia ei message_queuesta löytynyt.
* OUTIssa ei ollut lähtenyt MEMBERSHIP_EXPIRY-viestejä. Todennäköinen syy on viestipohjassa ollut Template Toolkit -koodissa ollut virhe.
* Kyytistä ihmeteltiin, että Vanhentuneet varaukset -raportille ei tule enää tuloksia sen jälkeen kun ExpireReservesOnHolidays-järjestelmäasetukseen muutettiin heillä, että varausten ei sallita vanhentua kiinniolopäivinä (esim. viikonloppuisin). Raportti on kuitenkin rakennettu niin, että varaus on poistettu seuraavana päivänä sen expirationdatesta. Muuten siihen tulee mukaan muitakin kuin vanhentumisskriptin poistamia.
* Tein palautekyselyn pääkäyttäjille versionvaihdon sujumisesta. Mikä meni hyvin/huonosti, mitä voisi parantaa jne.
* Lumpeissa löytyi vielä neljä yli 20 merkkistä viivakoodia, jotka aiheuttivat Perustiedot-näytöllä virheilmoituksen. Nämä ohjeistettiin korjaamaan käsin.
* Vaarassa käyttäjällä ei näkynyt Perustiedot-näytöllä Tuo/Vie-nappi, ongelma korjaantui selaimen välimuistin tyhjennyksellä.
* TäTissä huomasin sellaisen ongelman, että jos IntranetUserJS: Generate PIN codes -liitännäinen on aktivoitu, mutta sinne ei ole määritetty mitään asiakastyyppejä, niin kaikille generoituu nelinumeroinen pin-koodi. Kävin epäaktivoimassa liitännäisen, koska sitä ei TäTissä tarvita.
* Suljin signum-muutokseen liittyviä tikettejä ja jätin auki lähinnä OUTIn muutokseen liittyvät. Ne tehdään sitten, kun OUTIssa on saatu vietyä päätökseen projektia varten tarvittavat muutokset.
* Kyytissä ja OUTIssa on tullut käyttäjiltä ilmoituksia, että he ovat saaneet Virhe 500 -ilmoituksen, kun ovat lainanneet toiselle asiakkaalle jo lainassa olevia niteitä ja valinneet valinnan "Muista istunnolle", että lainaesto ohitetaan. Testasimme tätä Pirkko-Liisan kanssa sekä testeillä että tuotannossa superlibraian-oikeuksilla, perusvirkailijaoikeuksilla sekä minimioikeuksisilla tunnuksilla emmekä saaneet toistettua virheilmoitusta. Ehdotin ongelman johtuvan välimuistiongelmasta ja että käyttäjät voisivat tyhjentää selaimen välimuistinsa ja yrittää uudelleen. [Tiketti Koha-25x #254](https://github.com/KohaSuomi/Koha-25x/issues/254)

#### Johanna
* [Bug 23269: Add missing translations](https://github.com/KohaSuomi/Koha-25x/commit/d8e8ae4) (Koha-25x - ksdev/ks-0274-on-0243-KOHA-1563-prioritize-holds)
* [Bug 39140: Add missing pickup library check](https://github.com/KohaSuomi/Koha-25x/commit/3d24e77) (Koha-25x - ksdev/ks-0274-on-0243-KOHA-1563-prioritize-holds)
* [Merge branch 'master' of https://github.com/KohaSuomi/koha-plugin-broadcast-biblios](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/9718c6f) (koha-plugin-broadcast-biblios - master)
* [Fix col class](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/274f68a) (koha-plugin-broadcast-biblios - master)
* [Remove file](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/commit/4c67cde) (koha-plugin-broadcast-biblios - master)
* [KOHA-2221: Fetch messages again when cancelling](https://github.com/KohaSuomi/koha-plugin-print-pdf-notices/commit/8a659dc) (koha-plugin-print-pdf-notices - master)
* [KPVLT-11: Improve error message](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/6de3a2c) (koha-plugin-visual-label-tool - master)
* [Fix fetching itemnumber for dropdown](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/7975de9) (koha-plugin-visual-label-tool - ks25, master)
* [KPVLT-11: Fix error handling and improve messages](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/1dbbddd) (koha-plugin-visual-label-tool - master)
* [Remove console.log](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/commit/a0dca1e) (koha-plugin-visual-label-tool - master)
* [Add entry for ksdev/ks-0306-bug-40739-transfersblockcirc](https://github.com/KohaSuomi/koha-suomi-utility/commit/1097b4e) (koha-suomi-utility - master)
* [KohaSuomi/Koha - Siili: middle_name eli toinen nimi -kenttien tyhjennys](https://github.com/KohaSuomi/Koha/issues/2177);
Vastuutettu: johannaraisa, Anknite-cpu.
Kommentti: Nyt on tehty
* [KohaSuomi/Koha - Tarratulostuksessa ei saa luokkaa kirjaimella alkavasta signumista](https://github.com/KohaSuomi/Koha/issues/2197);
Vastuutettu: johannaraisa, Anknite-cpu.
* [KohaSuomi/Koha - Palautuksessa ei voi palauttaa useita kuljetettavia niteitä peräkkäin](https://github.com/KohaSuomi/Koha/issues/2200);
Vastuutettu: johannaraisa.
Kommentti: Tämä on nyt testeillä.
* [KohaSuomi/Koha - OUTI: Maksu ei siirtynyt Ceeposiin ja Koha antoi virheilmoituksen "Missing from configuration"](https://github.com/KohaSuomi/Koha/issues/2208);
Kommentti: Minkätyyppistä maksua tässä ollaan maksamassa? Vaikuttaa siltä ettei se payment_type ole oikein.
* [KohaSuomi/Koha - Lappi: Suomi.fi -viestien käyttöönotto](https://github.com/KohaSuomi/Koha/issues/2214);
Vastuutettu: johannaraisa.
* [KohaSuomi/Koha - Lappi: Testikantaan päälle kaukolainamoduuli](https://github.com/KohaSuomi/Koha/issues/2216);
Vastuutettu: johannaraisa.
Kommentti: Nyt on laitettu nämä testille.
* [KohaSuomi/Koha - Tulosta ilmoituksia -liitännäisessä peruuta-painiketta painaessa sivu ei päivity automaattisesti](https://github.com/KohaSuomi/Koha/issues/2221);
Vastuutettu: johannaraisa.
Kommentti: Testeillä on tähän korjaus, lataa sivu ctrl+F5:llä.
* [KohaSuomi/Koha-25x - Vaski: "Print slip and confirm" -painike ei toimi kun varauksen palauttaa ensimmäisen kerran](https://github.com/KohaSuomi/Koha-25x/issues/244);
Vastuutettu: johannaraisa.
Kommentti: Tämä on nyt testeillä testattavana.
Kommentti: Tähän löysin jo syyn, napin if-lauseesta puuttui kirjastopisteen tarkistus.
* [KohaSuomi/Koha-25x - Varauksen palautuksesta kaksi erilaista varausmodaalia](https://github.com/KohaSuomi/Koha-25x/issues/245);
Vastuutettu: johannaraisa.
Kommentti: Tuolle hold-found-modal-modaalille käännökset tehdään sillä uudella tavalla mitä käytetään myös asiakashakusivulla.
Kommentti: Vaskissa sekin näyttää olevan nyt englanniksi. Näyttävät laajentavan tuota tapaa tehdä käännöksiä, en tiedä auttaisiko tässä jos käynnistää plackin uudestaan.
* [KohaSuomi/Koha-25x - Tietuesiirtäjä: Muutokset -popparin kenttien tiedot yhdelle riville](https://github.com/KohaSuomi/Koha-25x/issues/247);
Vastuutettu: johannaraisa.
Kommentti: Tämä on testeillä, OUTIssa ei näyttänyt olevan tietueita listassa jossa tuo olisi näkynyt. Vaskilla kävin katsomassa ja näytti tälle,
Kommentti: Olen näköjään tämän jo neljä kuukautta sitten korjannut, mutta enää ei päde edes tuollainen määritelmä.
* [KohaSuomi/Koha-25x - Noutohyllyjen tuonti nextiltä testille](https://github.com/KohaSuomi/Koha-25x/issues/252);
Vastuutettu: johannaraisa.
Kommentti: Nyt on Vaskille kopioitu hyllyt nextiltä.
* [KohaSuomi/koha-plugin-visual-label-tool - Virhekäsittelyt eivät toimi oikein](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/issues/11);
Tiketti avattu.
Vastuutettu: johannaraisa.
* [KohaSuomi/koha-suomi-utility - Tätin SRU server (z3950_responder.pl) ei käynnistynyt](https://github.com/KohaSuomi/koha-suomi-utility/issues/100);
Tiketti avattu.


#### Emmi
* Kirkesiin ajettu cn_sort-kenttien korjaus [Kirkes: tietokannassa virheellisiä cn_sort-kenttiä](https://github.com/KohaSuomi/Koha/issues/2024)
* Testeille tehty muutoksia indeksointijonon kokoon ja muutos dokumentoitu
* Laskutustyökaluun lisätty testi-vipu, jolla voi generoida testilaskuja palvelimelle. Laskut generoituvat erilliseen test-hakemistoon ja ne merkitään tietokantaan failed-tilaan. Lisäksi niille tule oma failure_code:nsa. [Laskutusliitännäinen: Test-vipu run_finvoices.pl ajoon](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/35)
* Varaustyökaluun ei pysty tällä hetkellä viemään raportilla kuin alle 50 varausta. Ongelma näyttäisi poistuneen yhteisön versiossa 25.05.05, mutta korjaavaa committia ei ole vielä löytynyt. [Varausten vienti raportilta erämuokkaukseen epäonnistuu isoilla määrillä](https://github.com/KohaSuomi/Koha/issues/1980)

#### Lari

  Tiketit

  * [Yksityisoikeudellisten maksujen poistoajo ei päällä?](https://github.com/KohaSuomi/Koha/issues/2223) https://github.com/KohaSuomi/Koha/issues/2223
    [30.3.] Nämä ajot ovat olleet poikki kaikissa kimpoissa versionvaihdosta lähtien johtuen siitä, että ajastetun ajon $NEWTRIG-skripti puuttuu tuotannoista, eikä ajot siksi ole menneet läpi.

    [30.3.] Nyt kaikkin tuotantoihin on korjattu ajastettu ajo. Ajautuu siis ensi yöstä taas päivittäin ja missatut maksutkin tulevat käsiteltyä.

  * [Hyllyvarausraportille näppäintoiminto pudotusvalikkoihin](https://github.com/KohaSuomi/Koha/issues/2210) https://github.com/KohaSuomi/Koha/issues/2210
    [30.3.] Poistin holds-to-pull-skriptistä "zero-width space"-lisäykset jotta näppäinkomennot tarttuvat suodatusarvoihin ja tein mm. Hyllyssä- ja Noutopaikassa-sarakkeille kustomoidut filtterit. Testattavana testeillä.

    [30.3.] Lisäsin saman kustomoidun filtteröinnin käyttöön näille muillekin sarakkeille, millä on pudotusvalikko ja missä voi olla useampi arvo valittavana. Testattavana testeillä.

  * [Varauksen noutomuistutusilmoituksille sallittavat viestienvälitystavat](https://github.com/KohaSuomi/Koha/issues/2190) https://github.com/KohaSuomi/Koha/issues/2190
    [31.3.] Sovittiin kehittäjäpalsussa että siivotaan ei-halutut viestivalinnat pois asiakkailta tietokannasta ennemmin kuin muutetaan skriptin toimintaa (vipu tiettyjen toimitustapojen pakottamiseksi), jotta skripti toimii käyttöliittymässä näkyvien(/piilotettujen) valintojen mukaisesti. Ei maksa mittee.

  * [OUTI: Maksu ei siirtynyt Ceeposiin ja Koha antoi virheilmoituksen "Missing from configuration"](https://github.com/KohaSuomi/Koha/issues/2208) https://github.com/KohaSuomi/Koha/issues/2208
    [31.3.] Toimimaton nappi on piilotettu Lainausnäkymästä. Testattavana testeillä.

  * [Maksujen muodostus hidasta versionvaihdon jälkeen](https://github.com/KohaSuomi/Koha/issues/2233) https://github.com/KohaSuomi/Koha/issues/2233
    [1.4.] Tutkimusteni mukaan accountlines-tauluun on tullut versionvaihdossa uusi sarake old_issue_id ja issues/old_issues-tauluun checkin_library joilla voi olla merkitystä. Reserves-taulussa uutena deleted_biblionumber.

  * [Vaskille käyttöön versiopäivityksen yhteydessä varauksen noutomuistutuksen muutokset](https://github.com/KohaSuomi/Koha/issues/2198) https://github.com/KohaSuomi/Koha/issues/2198
    [1.4.] Ajettu days_in_advance NULL -> 1.

  * [Helle, asiakkaalle muodostunut Varauksen noutomuistutus voimassa olevasta lähiaikoina vanhenevasta varauksesta](https://github.com/KohaSuomi/Koha/issues/2227) https://github.com/KohaSuomi/Koha/issues/2227
    [1.4.] Lisäsin testeille noutomuistutusten luontiskriptiin ehdon, että vain varaukset, joiden tila on W"odottaa" käsitellään. https://github.com/KohaSuomi/Koha-25x/commit/bb3d199fc06dfeb9aa293498546327d525c198e2  Muutos viety testeille.

    [1.4.] Testaus:  Tee asiakkaalle kaksi varausta, jotka vanhenevat x päivän päästä ja tärppäytä toinen niistä. Varmista, että vanehenemispäivä on edelleen x päivän päästä. Tarkista, että noutomuistutus, joka muodostuu asiakkaalle valittuna ajankohtana sisältää vain tärpänneen varauksen.

  * [Self service-pluginin repositorion korvaaminen Koha-Suomen versiolla.](https://github.com/KohaSuomi/Koha/issues/1847) https://github.com/KohaSuomi/Koha/issues/1847
    [2.4.] Plugin on poistettu käytöstä.

  * [Lumme: uusien maksutyyppien lisäys mitätöintiajoon](https://github.com/KohaSuomi/Koha/issues/2143) https://github.com/KohaSuomi/Koha/issues/2143
    [2.4.] Maksutyypit on lisätty entisten lisäksi maksujen mitätöintiajoon. Ajautuvat joka päivä, joten huomenna poistuvat kaikki 3v ja sitä vanhemmat, joiden kuuluu poistua.

  * [SIP2-autentikointi lokittuu virheellisesti verkkokirjastossa tapahtuvaksi](https://github.com/KohaSuomi/Koha/issues/2079) https://github.com/KohaSuomi/Koha/issues/2079
    [2.4.] Muutos on tuotannoissa.

  * [EDItX Koodiin jääneen debuglokituksen poisto](https://github.com/KohaSuomi/koha-plugin-editx/issues/11) https://github.com/KohaSuomi/koha-plugin-editx/issues/11
    [2.4.] Tämä muutos koski EDItX-pluginia eikä SIPoHTTP:ta kuten tiketissä virheellisesti mainittiin. Korjaus on paikallaan tuotannoissa ja testeillä (ja nexteillä).

  Kommitit

  * KohaSuomi/Koha-25x
    * `6276f0d` [30.3.] KOHA-2210 Use custom filter plugin in template for filter typing and exact matches
    * `8c28b94` [30.3.] KOHA-2210 Use custom list filter for all dropdown columns
    * `bb3d199` [31.3.] Only deal with reserves with waiting status

  * KohaSuomi/koha-plugin-ceepos-integration
    * `fa7053e` [31.3.] KOHA-2208 hide paycollect button in circulation.pl that doesn't work with Ceepos

#### Kodo
* Koha versiopäivityksen yliheitto + ajot;
yliheitto ja ajot ajettu sunnuntain 2026-03-22 – maanantain 2026-03-23 välisenä yönä.
* [FacetSortingLocale-järjestelmäasetuksesta puuttuu kielivaihtoehdot](https://github.com/KohaSuomi/Koha-25x/issues/246);
tilanne kuvattu: ongelma ei ilmene testeillä; TäTi ja Siili ok; muissa kimpoissa kielivaihtoehdot näkyvät/puuttuvat vaihtelevasti. Kokeellinen korjaus tehty, mutta tulos laiha.
* [Lainaus ja palautus -sivujen sivuvalikossa väärä linkki](https://github.com/KohaSuomi/Koha-25x/issues/249);
linkki korjattu kiireellisenä tuotantoihin; pysyvämpi korjaus tehty ja tulossa buildissa tuotantoon; tiketti jätetty auki odottamaan tuotantoon päätymistä.
Seuraavana varmistus viikkopäivityksen jälkeen, että pysyvä korjaus on tuotannossa, ja tiketin sulku.
* [EDItX-plugin - koha-plugin-editx](https://github.com/KohaSuomi/Koha-25x/issues/83);
hankinta tuotti `HANK_`-alkuisia viivakoodeja kimpoissa joissa halutaan automaattigeneroitu viivakoodi, korjaus tehty EDItX-pluginille ja testattu toimivaksi.
Commitoitu ja pushattu, ei vaadi muita toimenpiteitä, seuranta mahdollisten uusien havaintojen varalta.
* [Vanhentuneiden varausten peruuttaminen (crontab)](https://github.com/KohaSuomi/Koha-25x/issues/204);
tilanne todettu tarkistettavaksi ensi viikolla, vanha cronjob deprekoitu ja turha, mutta ei toiminnallista haittaa.
Seuraavana crontab-rivien läpikäynti kimpoittain ja päätös vanhan rivin poistosta / uuden rivin varmistus.
* [99-sanomien käsittely SIP-palvelimen ohi](https://github.com/KohaSuomi/Koha-25x/issues/192);
Bibliothecan automaattien yhteensopivuusongelma (97 resend / checksum/sequence -epäily, mahdollinen rivinvaihto/carriage return -ero)
Korjauksen testauksesta sovittu Bibliothecan kanssa.
Seuraavana testaus Bibliothecan automaatilla, jotta korjaus voidaan validoida ennen uudelleenkäyttöönottoa.
* Runsaasti erilaisia SIP-tunnusongelmia monissa kimpoissa.
Tunnuksia putoillut kyydistä versiopäivityksessä, korjailtu sitä mukaa kun tulee vastaan.
Seuraavana tarkistettava kaikkien kimppojen sip-konfiguraatioiden oikeellisuus

## Viikko 13

Versionvaihdon vuoksi normaaliin viikkopalaveri aikaan pidettiin versionvaihdon tilannekatsaus.
  
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
