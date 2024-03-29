---
layout: single
permalink: /paakayttajat2023
header:
  overlay_color: '#5e616c'
  overlay_image: /assets/images/cropped-pexels-photo-113850.jpeg
toc: true
title: 'Koha-Suomen pääkäyttäjäryhmän muistiot 2023'
---

Koha-Suomen pääkäyttäjäryhmä kokoontuu kerran viikossa. Ylimmäisenä on aina uusin muistio.

## Viikko 51

Aika: 19.12.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Anni Rajala (Vaski), Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Anneli Österman ja Lari Strand (Koha-Suomi), Leena Kinnunen ja Pia Kusmin (Lappi), Tuomas Kunttu ja Roosa Väisänen (Kyyti), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* Finna-muutos: varaustunnus asiakasmääreenä HOLDID (holdid-parametrinimellä) Finnaan, jotta kutsumanimi-tieto vapautuu välitettäväksi omana tietonaan Finnaan. Jos uutta kutsumanimi-kenttää ei haluta näyttää/muuttaa Finnassa/Finnasta, muutos on tarpeeton ja voidaan jatkaa Finnan käyttöä ilman muutosta sellaisenaan ja ylläpitää othernames-tietoja pelkästään Kohassa. Jos tieto halutaan näkyviin Finnaan, pitää sopia aikataulu Finna-pluginin ja Finna-ympäristöjen muutokselle. Pitää sopia tapahtuvaksi samaan aikaan.
* [Tehdäänkö marc-mäppäysmuutos?](https://github.com/KohaSuomi/Koha/issues/693)
  * tehdään, tieto lisätty tikettiin.
  * Pääkäyttäjät tekevät omiin tuotantoihin ja testeille (tarvittaessa myös nexteille) tarvittavat mäppäysmuutokset, jonka jälkeen pitää ajaa rebuildbiblios-ajo.
* BTJ:n linkkien korjaaminen keskitetysti? www.btj.com --> armas.btj.fi
  * Päivi tekee tiketin ( https://github.com/KohaSuomi/Koha/issues/982 )ja Anneli tutkii, voiko käyttää kuvailun erämuokkauksella. Jos ei voi, pitänee tehdä jonkinlainen skripti.
* [Vkon 51 päivitys](https://github.com/KohaSuomi/Koha/discussions/980)
* Onko kaikilla [Koha-Suomi-valikko](https://koha-suomi.fi/dokumentaatio/jarjestelmaasetukset/#intranetnav) Kohassa?
  * Redmine-linkit voisi poistaa, jos sellaisia on.
* [Joulutervehdys](https://github.com/KohaSuomi/Koha/discussions/979)
* [Testikantojen tilanne](https://github.com/KohaSuomi/Koha/discussions/969)
  * Anneli pyytää Finna-toimistoa haravoimaan testikannat uudelleen kunhan kaikki kannat on tehty uudelleen.
* [Tietueen Perustiedot -näytön kohdehenkilö-asiasanalinkki ei toimi, kun kentällä on osakenttä 600c](https://github.com/KohaSuomi/Koha/issues/459)
  * Indeksointi- ja tiedonhakuryhmältä päätös, että muutetaan järjestelmäasetus ongelman korjaamiseksi.
  * Pääkäyttäjille tehtäväksi muuttaa tiketissä mainittu järjestelmäasetus.

Etelästä pohjoiseen

**Vaara**
* Finnan selitys viime viikolla ilmoittamastani maksuongelmasta: "Tämän pitäisi nyt olla kunnossa ja korjattu. Tutkittiin, että saattoi harvassa tapauksessa esiintyä visuaalinen virhe, jossa näkyi väärä summa maksunäkymässä. Jos asiakas olisi jatkanut maksamaan, niin summa olisi ollut oikea."
* Päivi korjannut MARC-virhelistan mukaisia virheitä kuvailutietueissa. Tehty tiketti 006-kenttien poistosta muissa kuin moniviestimissä. Vanhoja tikettejä on olemassa myös muista korjauksista, mm. emottomien osakohteiden poistopyyntö (https://github.com/KohaSuomi/Koha/issues/348) on melkein vuosi sitten tehty. Näitä vanhoja tikettejä pitäisi saada tehtyä ennen kuin ISBD- ja RDA-konversioita ajetaan.

**Lumme**
* Tehty signumien korjausajo varastokirjoille, sillä aikojen saatossa käytetty useaa erilaista merkitsemistapaa. Korjattu signumit myös jo lakkautettujen kirjastojen niteistä.
* Raporttikirjaston siivous saatu loppuun.

**Vaski**
* Kyseltiin onko tarvetta tehdä tikettiä hyllyvarausraportin suodatushaku-kenttää koskevasta ongelmasta (merkkejä putoaa pois nopeasti kirjoittaessa). Todettiin, että ei tarvetta toistaiseksi, eikä kannata senkään takia kun viime aikoina on ollut keskustelua mahdollisesta siirtymisestä Varausjono-raportin käyttöön.
* Otettu eilen käyttöön uusi nidetyyppi sellaisille esineille, joita saa varaaminen on sallittu ainoastaan niteen kotikirjastoon. Kohassa edellyttää, että Laina- ja maksusäännöt -sivulle on tavallisten laina- ja maksusääntörivien lisäksi tehty "Oletusvaraussääntö nidetyypeittäin". Oletusvaraussääntö nidetyypeittäin löytyy laina- ja maksusääntösivun lopusta, kuvassa Vaskin tekemä oletusvaraussääntö:

  ![kuva](https://github.com/KohaSuomi/kohasuomi.github.io/assets/44638512/1f306b93-cd90-4c1e-9ad4-633f63bf89a8)

  * Kun oletusvaraussääntö on käytössä, Finna herjaa englanniksi "The supplied pickup location is not valid" jos asiakas yrittää valita ei-sallitun noutokirjaston. Tälle virhetekstille on mahdollista lisätä kielikäännökset local > languages -alta löytyviin ini-tiedostoihin. Tiedostoihin pitää lisätä rivi, jossa virheilmoitus on tismalleen samalla tavalla kirjoitettuna eli tämän näköinen rivi:
  
  ```The supplied pickup location is not valid = "Tämän aineiston voi varata noudettavaksi vain siihen kirjastoon, jossa se parhaillaan sijaitsee."```

  * Tuota käännöstekstiä voi muotoilla toki paremmaksi, meillä pohdiskeltiin mikä olisi asiakkaalle kaikista selkein tapa ilmaista ja kotikirjasto-termin sijaan päädyttiin tuohon ilmaisuun. Englanniksi meillä on käännetty "This material can only be reserved for pick-up at the library where it is currently located." ja ruotsiksi "Detta material kan endast reserveras för avhämtning på det bibliotek där det för närvarande finns."
  * Näitä kielikäännöksiä kun Finna-toimistolta kysyttiin, niin sieltä vastattiin että *"Normaalisti ILS-järjestelmien ilmoitusten käännöksille on varattu oma paikkansa, mutta ainakaan tällä hetkellä Kohan tapauksessa järjestelmä ei tätä ymmärrä, joten käännökset on lisättävä muiden käännösten joukkoon. Itse lisätyt käännökset voi toki olla hyvä tarkastaa siinä vaiheessa, kun ilmoitusten käännökset päivittyvät yhteisesti kaikille, mutta varsinaista ongelmaa aikanaan tulevasta päivityksestä ei pitäisi kuitenkaan tulla."*
 
**OUTI**
* Käyttäjältä tuli toive, että jos lainassa olevaa nidettä yrittää poistaa Perustiedot-näytön toiminnolla ”Poista valitut”, ohjelma ilmoittaisi ”Ei voi poistaa: nide on lainassa”. Tämä ilmoitu tulee, jos lainassa olevaa nidettä yrittää poistaa niteiden muokkaussivulla. Anneli tiesi kertoa, että versiossa 23.11 tulee paremmin näkyväksi, ettei nidettä voi poistaa eli toiminnossa ”Niteiden poisto eräajossa” tulee sarakerivin eteen punainen ruksi ja sarakkeen väri on keltainen. Ei lisätä ilmoitusta nykyiseen versioon.
* Jos käyttäjällä ei ole oikeuksia laskutustyökaluun, tulee ilmoitus ”Virhe 403”. Päätettiin, ettei ilmoitusta tarvitse muuttaa.
* Finna-toimiston kanssa selvitetty asiakkaan maksuissa näkyviä palautuskehotusten tekstejä. Tiketti: https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/21
* Aspassa oli tullut palautettavaksi toisen OUTI-kirjaston nide, jolle Koha ei antanut palautustilanteessa ilmoitusta, että nide pitäisi kuljettaa kotikirjastoon, vaan nide jäi aivan kuin kellumaan palautuskirjastoon. Selvisi, että nide oli yhden OUTI-kirjaston siirtolainakokoelmassa. Ilmeisesti siirtolainatoiminto on huonontunut entisestään, koska se ei antanut ilmoitusta, että nide kuuluu jonkin kirjaston siirtolainakokoelmaan. Aiemmassa Koha-versiossa ohjelma vielä antoi ilmoituksen siirtolainakokoelmasta, vaikkei se asettanut nidettä kuljetustilaan. OUTI-kunta, joka on vielä käyttänyt siirtolainakokoelmia omissa pienissä kirjastoissa, luopui niiden käytöstä nyt kokonaan. 

**Lappi**
* Maksujen poistoajo-skriptin käyttöönotosta keskustellaan vielä Lapissa. EDIT: maksujen poistoajo otetaan myös Lapissa käyttöön 1.1.24.
* Käyttäjältä on tullut kyselyä Kohan ajojen aikatauluista koskien mm. viestien lähetysaikaa ja maksujen muodostumisaikaa. Suunnitellaan tiedotusta asiasta.

**Kyyti**
* Pääkäyttäjät ovat keskenään miettineet työtehtäviä mm. vuosikellon muodossa.
* Kotkaan tilattu yksi Bibliothecan Rfid-harava testiin.

**Siilinjärvi**
* Siilin pitäisi olla valmis vanhentuneiden maksujen mitätöintiin
* Ei muuta erikoista
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-51) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 50

Aika: 12.12.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Reetta Pihlaja (Siilinjärvi), Leena Kinnunen ja Pia Kusmin (Lappi), Elina Uotila (Kirkes), Roosa Väisänen (Kyyti), Anneli Österman, Emmi Takkinen, Lari Strand (Koha-Suomi)

**Yhteiset**
* [Varaustunnisteen säilyttäminen/muuttaminen](https://github.com/KohaSuomi/Koha/issues/896) - miten toimitaan?
* [Viikon 50 päivitys](https://github.com/KohaSuomi/Koha/discussions/958)
* [Koha-Suomen asiantuntijaryhmän muistio 10/2023](https://github.com/KohaSuomi/Koha/discussions/963)
* Versionvaihdon ja nextien tilanne
  * outi-next tehty, sitä ei redusoida eli se pitää tehdä vielä kertaalleen uusiksi. Tällä hetkellä vanha redusoitu kanta alla.
  * loput työn alle, kunhan testikannat on tehty uudelleen ja redusoitu (ja testattu redusointiskripti)
  * Elasticsearch pitää päivittää uudempaan versioon. Nykyisen version 6.8 tuki loppui ja uudessa Koha-versiossa pitää olla 7 tai 8 versio.
  * Annelilla release notesien läpikäynti vielä kesken.
* [Testikannat uusiksi tänään](https://github.com/KohaSuomi/Koha/discussions/948)
  * Vaski-testiä ei redusoida
  * työ tehdään illalla, kannat toivottavasti valmiiksi tämän viikon aikana ja käytössä ensi viikolla.

**Vaara**
* henkilötietoja sisältäneitä raportteja on suojattu salasanalla, jotta kaikki eivät pääse ajamaan niitä
* Finnassa havaittiin omituinen maksuongelma. Asiakas oli yrittänyt 1.12. maksaa 22,80 euron maksujaan verkkokirjastossa, mutta maksu ei koskaan mennyt perille asti Paytrailiin (ei näy maksettuna). Asiakkaan laittamien kuvakaappauksien mukaan välillä summa oli näyttänyt 80,22 euroa, mikä on todella omituista. Paytrailissa ei oteta kantaa, koska maksu ei näy heidän järjestelmässään.
* Irina kysyi, onko muilla ongelmia itsepalvelutoiminnon kanssa. Vaarassa Kiihtelysvaaran kirjastossa on toistuvasti ongelmia itsepalvelulainauksen päällä olemisen kanssa. Tähän ei saatu mitään vertaisapua eikä myöskään verkkoyhteyksistä vastaava Meita ole saanut asiaa kuntoon.

**OUTI**
* Otettu käyttöön uudet kirjastokortit, joiden tunnus alkaa sanalla OUTI+7 numeroa.
* Lumijoen kirjastossa ollaan ottamassa käyttöön Koha-Ceepos-maksurajapinta.
* Oulun kaupungin kaikki palvelimet siirretään Istekille. Oulun Ceepos-palvelin siirretään viikonlopun 20.1.-21.1.2024 aikana. Mikään ei pitäisi muuttua tietoliikenneyhteyksissä yms. määrityksissä.
* Otettu käyttöön asiakkaan tiedoissa Muu nimi -kenttä henkilöasiakkaiden kutsumanimille. Sähköposteina meneviin asiakasviesteihin on lisätty ehto, jos asiakkaalla on tallennettu kutsumanimini, tulee se tervehdystekstiin. Jos kutsumanimeä ei ole tallennettu, tulee etunimi. Yhteisöasiakkaille ja kaukolainakirjastoille kenttää ei otettu käyttöön, näille tervehdykseen tulee sukunimi-kentän tiedot.
* Aspassa tullut vastaan tuplamaksutapaus, jossa lainan uusintatilanteessa klo 00.04 oli järjestelmä luonut asiakkaalle uudestaan maksimimäärän myöhästymismaksuja. Tiketti: https://github.com/KohaSuomi/Koha/issues/961
Vastaavia tapauksia on tullut tilanteissa, joissa maksuja on maksettu puolen yön aikaan, jolloin maksuajo on ollut meneillään. Pääkäyttäjäpalaverissa 25.7.2023 on sovittu, että Vaskissa kokeltaisiin onnistuuko maksunappulan disablointi. Mikko tarkistaa asian, onko disablointia kokeiltu tehdä.

**Lumme**
* Ei raportoitavaa, perusylläpitoa.

**Siilinjärvi**
* Ei mainittavaa

**Lappi**
* Puolivuosittainen käyttäjätunnusten tarkistus menossa johtajilla ja esihenkilöillä. Tarkistetaan käyttöoikeuden voimassaolo, ei kuitenkaan sitä, mitä oikeuksia käyttäjillä on.
* Muuten ei raportoitavaa.

**Kirkes**
* Tietokannasta oli epähuomiossa poistettu suuri joukko niteitä, mutta ne saatiin kehittäjien avustuksella onneksi palautettua.
* Laskutusrajapinnan käyttöönotto ja siihen liittyvä työ jatkuu Järvenpäässä ja Mäntsälässä.
* Keskusteltiin henkilökunnalta tulleesta käännösmuutostoiveesta ja todettiin, että niteistä puhuttaessa "Huomautus virkailijalle" on parempi kuin "Viesti virkailijalle". Tiketti:  https://github.com/KohaSuomi/Koha/issues/970

**Kyyti**
* Kotkasta muutama kävi Espoossa tutustumassa Lippulaiva-kirjastossa käytössä olevaan Lirpiin (Library resource planner).

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-50) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 49

Aika: 5.12.2023 klo 9.15 <br />
Läsnä: Anneli ja Lari (Koha-Suomi), Piia Semenoff (OUTI), Päivi Knuutinen (Vaara), Kati Sillgren, Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Annika Helastila (Kirkes), Leena Kinnunen ja Pia Kusmin (Lappi)

**Yhteiset**

* [Testikantojen uusiminen ja redusointi](https://github.com/KohaSuomi/Koha/discussions/948)
* action_logs-taulujen ajot
  * kaikissa kimpoissa aloitettu nyt kuukausittainen vienti vuositauluihin.
  * yhteen arkistotauluun vienti vielä uuden pohdinnan alla. Testataan viewn/näkymän toimivuutta.
* [Viikon 49 päivitys](https://github.com/KohaSuomi/Koha/discussions/950)
* [Versio 23.11 julkaistu](https://koha-community.org/koha-23-11-released/)
* [Koha-seminaarin aineisto](https://koha-suomi.fi/dokumentaatio/koulutukset/#koha-seminaari-28112023)
  * Tiedote: [Koha-seminaarin satoa 2023](https://github.com/KohaSuomi/Koha/discussions/952)
* [Näin saat SQL-kyselyyn salasanan](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#miten-saa-raportille-salasanan-kyselyn)

Etelästä pohjoiseen

**OUTI**
* Tarrojen tulostuksesta tehty meille kehitysehdotus: kun niteet vedetään/viedään tarratulostusjonoon, niin olisi hyvä, jos niteet tulostuisivat myös siinä järjestyksessä tarra-arkille tai tarra-rullalle. -> kehitysehdotus-tiketti
* Oulun elokuvakeskuksen ja sarjakuvakeskuksen kirjastojen ja Oulun kaupunginkirjaston välinen logistiikka loppuu, joten eilen muutin niiden niteitä "Saatavana, ei lainattavissa"-tilaan ja käsittelin niiden kokoelmiin kohdistuvat voimassa olevat varaukset.
* OUTIssa on tehty ajo, jossa asiakkaille (runsas 5000 asiakasta) lisättiin viestikenttään huomautus "Tarkista onko asiakkaan matkapuhelin- ja tekstiviesti numeroon -kentissä samat numerot. Korjaa tarvittaessa." Näillä asiakkailla on eri numerot matkapuhelinnumero ja SMS-kentissä. Ajo liittyy tikettiin: https://github.com/KohaSuomi/Koha/issues/835#issuecomment-1827861250.
* Asiakkaalta puuttui varaustunniste. Myös testillä varaustunniste puuttui. Ei ole tullut  muualla vastaan. OUTIssa ei onneksi ollut enempää vastaavia tapauksia.
* Kodo teki eilen pyynnöstä OUTIin API-tunnukset Raportterin käyttöä varten. Toimitan tunnuksen Larille.Tässä Larin ohje ja teknisempi dokumentaatio: https://github.com/KohaSuomi/koha-plugin-report-services/wiki ja https://github.com/KohaSuomi/koha-plugin-report-services/blob/master/README.md. 

**Vaara**
* ei erityisempää, normaalia ylläpitoa
* maanantaina omituinen ongelma Päivin pääkäyttäjätunnuksen kanssa. Aamulla toimi ensin ihan kunnolla kaksivaiheisen tunnistaumisen kanssa, mutta jossain vaiheessa alkoi temppuilemaan ja vaati tunnistautumista jatkuvasti. Tunnuksella ei voinut tehdä töitä. Muualta Vaaroista ei tullut mitään ongelmaviestejä, joten ihmettelin asiaa Larille eikä Vaarassa näkynyt tietokannan kautta mitään ongelmaa. Toimin tunnin verran toisella käyttäjätunnuksellani. Ilmeisesti kyseessä oli selaimen keksiongelma tai jotain, sillä ruokatunnin jälkeen suljin selaimen ja kirjauduin uudelleen pääkäyttäjätunnuksellani ja kaikki toimi kuten pitääkin.

**Helle**
* Toivottu mahdollisuutta tehdä kerralla nidevaraus useammalle kuin yhdelle niteelle. Ehdotus ei saanut palaverissa kannatusta. Lari vinkkasi yhteisön tiketin https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=15565

**Lumme**
* Normaalia ylläpitoa.
* Lumme-kirjastoihin on nyt hyväksytty yhteiset kimppakohtaiset käyttösäännöt.
* Asiakastiedot on hyväksytty vanhenemaan viidessä vuodessa, jos asiakas ei käytä kirjaston palveluja. Vanhentuneiden asiakastietojen poistoajoa yritetään tehdä vielä tämän vuoden puolella.

**Kyyti**
* Miten saa salasanan raportteihin? Anneli tekikin nopeasti [ohjeen](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#miten-saa-raportille-salasanan-kyselyn), kiitos.
* Kyyti oli reilu puoli tuntia alhaalla torstaina 30.11. klo 17.33-18.xx.  Message_queue oli lukossa.
* Iitin kirjaston varaston niteisiin ajettu viime viikolla [muutos](https://github.com/KohaSuomi/Koha/issues/937) remontin takia.

**Kirkes**
* Kerava sai laskutustyökalun tuotantokäyttöön (woop, woop!), muut kunnat työstävät vielä.
* Kiinnostusta näyttää vain kolme viimeistä numeroa kirjastokortista asiakkaalle lähtevässä ilmoituksessa. VASKIssa käytössä koodirimpsu, jota testataan.

**Lappi**
* Lapissa jälleen neljä pääkäyttäjää, kun Noora Suvanto Tornionlaakson kirjastosta on palannut töihin
* Tarkoitus ottaa käyttöön no-reply-toiminto sähköposteihin.
* Ei muuta raportoitavaa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-49) - [Palaa sivun alkuun](/paakayttajat2023)
  
## Viikko 47 muistio

Aika: 21.11.2023 klo 9.15 <br />
Läsnä: Anneli Österman ja Emmi Takkinen (Koha-Suomi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Leena Kinnunen ja Pia Kusmin (Lappi), Kati Sillgren, Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Elina Uotila (Kirkes, hetken alusta), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti)

**Yhteiset**

* [Varaustunnisteen generointi](https://github.com/KohaSuomi/Koha/issues/896) - miten toimitaan? Yhtenäinen linja olisi hienoa, jotta ei tarvitse ylläpitää useampia JS-rimpsuja.
  * Pääkäyttäjät testaavat kumpaakin versiota testeillä ja tehdään lopullinen päätös parin viikon päästä.
* [Tietopyyntö](https://github.com/KohaSuomi/Koha/wiki/Tietopyynt%C3%B6)-ohjeistus lisätty.
* [Automaattinen nidetyypin valinta](https://github.com/KohaSuomi/Koha/issues/336) / Emmi
  * Päätettiin kokeilla toista tapaa, jossa nidetyyppi päätellään muiden vastaavilla arvoilla olevien niteiden nidetyypistä ja katsotaan sitten, miten edetään.

Pohjoisesta etelään

**Vaara**
* ei erityistä mainittavaa, normaalia ylläpitoa
* Finnassa piilotettu Peru kaikki varaukset-painike

**Lappi**
* Normaalia ylläpitoa

**Helle**
* Tarkkaan hakuun toivottu lisää valmiiksi valittavia hakuehtoja (sarjan sisäinen numerointi 490v, nimekkeen numerointitieto 245n)

**OUTI**
* Vielä kesken Muu nimi -kentän näkyviin saaminen verkkokirjastoon asiakkaan Omat tiedot -sivulle asiakkaan kutsumanimeä varten. Koska Muu nimi -kentässä käytettiin aiemmin varaustunnusta, Larin on tehnyt Finnan testiympäristössä olevaan Finna-pluginiin tarvittavia muutoksia holdid- ja other name -kenttien osalta. Vaatii muutosta vielä myös Finnan päähän.
* OUTIssa piilotettu myös Finnasta ”Peru kaikki varaukset” -toiminto.
* Vaalan kirjaston Ceepos-palvelin vaihtuu ke 22.11. Tiketti: #860

**Lumme**
* Normaalia ylläpitoa.

**Kyyti**
* Valkealan lähikirjasto suljettu muuton vuoksi loppuvuoden. Viime viikolla tehtiin siihen liittyvät nidetilojen muutokset.
* Nostin esille vanhan Redmine-tiketin 1849 ja että miten edetään 005-kentän päivittymisen kanssa. Siirsin palaverin jälkeen tiketin Githubiin [#924](https://github.com/KohaSuomi/Koha/issues/924).

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-47-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 46 muistio

Aika: 14.11.2023 klo 9.15 <br />
Läsnä: Anni Rajala (Vaski), Reetta Pihlaja (Siilinjärvi), Hanna Ikonen (Lumme), Päivi Knuutinen (Vaara), Annika Helastila ja Elina Uotila (Kirkes), Tuomas Kunttu (Kyyti), Anneli Österman ja Johanna Räisä (Koha-Suomi), Kati Sillgren (Helle)

**Yhteiset**
* [Viikon 46 päivitys](https://github.com/KohaSuomi/Koha/discussions/914)
* [Koha-seminaarin ilmoittautuminen ja ohjelma](https://github.com/KohaSuomi/Koha/discussions/850)
* [Tarvetta tiketeille Githubiin](https://tiketti.koha-suomi.fi/issues/5585)?
* Jos nidevaratulta niteeltä puuttuu signum, [ei se tule hyllyvarauslistalle](https://github.com/KohaSuomi/Koha/issues/868)
  * kannattaa huolehtia, että lehdille tulee signum. Helpointa se on kun huolehtii, että lehtitilauksen Luokka-kentässä on signum valmiina, jolloin se tulee automaattisesti myös niteelle.
  * kannattaisiko signum-kenttä laittaa pakolliseksi?

```
select biblionumber, itemnumber 
from items
where itemcallnumber is null
and itemnumber in (select itemnumber from reserves)
and notforloan=0
```
* perjantaina taas bugi-perjantai klo 13.

Etelästä pohjoiseen

**Vaski**
* Uusi erikoistila tarramuutosta vaativien niteiden kiinnisaamiseksi otettu käyttöön.
* Puppe-saapumisvalvontatyökalun käyttöönotto etenee, henkilökunta pääsee testaamaan joulukuussa kun Broomworks tulee paikan päälle.

**Kirkes**
* Mietiskellään nidetyyppien laina- ja varaussääntöjä.
* laskutusrajapinnan käyttöönotto matelee eteenpäin.

**Siilinjärvi**
* Kohassa ei mitään mainittavaa, onneksi, koska poissaolotilanne hankala.
* Kysytty miten muualla reagoidaan asiakkaan pyyntöön palauttaa varaukset, jos asiakas on ne itse vahingossa Finnassa poistanut Peru kaikki varaukset -valinnalla. Käytännöt vaihtelivat, mutta Vaskissa on piilotettu koko painike (kiitos Roosa!): Painikkeen saa piiloon lisäämällä seuraavan CSS-määrityksen tiedostoon custom.less tai custom.css (kommenttirivi vapaaehtoinen):

//Peru kaikki varaukset -painikkeen piilotus
#cancelAll {
  display: none;
} 

**Lumme**
* Perusylläpitoa.
* Kehitysehdotus: kun tehdään niteiden eräpoisto, Koha herjaisi, jos jokin poistettava nide on lainassa. Päätettiin odottaa tulevaa Nextin testiversiota, josko asiaan olisi tulossa parannusta ja katsoa sitten asiaa uudestaan. Tällä hetkellä voi hyödyntää Lainassa-saraketta, joka tulee esiin poistettavien kirjojen listassa, jos yksikin poistettava nide on lainassa.

**Vaara**
* perusylläpitoa ja erilaista siivousta/korjausta Vaarassa ja TäTissä

**OUTI**
* Asiakkaalle oli lähtenyt viime viikolla sähköpostia vaikka hänellä on asetuksissa pelkät koosteviestitäpät. Vaarassa törmätty samanlaiseen tilanteeseen. Tehdään tästä tiketti.
* Kun palauttaa uudestaan noutoa odottavan varauksen ja klikkaa jompaa kumpaa popparin valinnoista (OUTIssa ne ovat Tulosta kuitti ja vahvista ja Vahvista varaus), niin noutoaika jatkuu eräpäiväkalenterin mukaan kuin se jäisi ensimmäistä kertaa kiinni. Tästä on tiketti: : https://github.com/KohaSuomi/Koha/issues/646. Tiketissä on kommentoitu, että "tämä on korjattu yhteisössä, joten joko korjaus tulee meille ensi kevään versiovaihdossa tai sitten tuomme korjauksen jo tähän nykyiseen käyttämäämme versioon". Testataan Nextillä, kun ne saadaan pystyyn uudella versiolla. 
* OUTIssa oli koha-jumi to 9.11. klo 9.34. OUTIn jumimisen takia laitettiin samana päivänä kaikkien kimppojen tuotantoihin viestien käsittelyn muutos, joten nyt viestit lähtevät 5 min välein, maksimissaan 500kpl kerrallaan. https://github.com/KohaSuomi/Koha/issues/908
* Kirjastoauto Kaunon varausten noutoajan pidennys tehty tänään 14 vrk -> 21 vrk.
* Finna ei tarkista mitä puhelinnumerokenttään täytetään, sinne voi kirjoittaa mitä tahansa merkkejä. Tämä koskee kaikkia kimppoja. OUTI tekee tiketin ja lähettää viestiä kansalliskirjastolle.

**Kyyti**
* Esittelin, miten olin Excelin avulla rakentanut tarvittavat arvot AutoItemtype-järjestelmäasetukseen.
* Miten saa muutettua maksutyypin kuvausta, josta puuttuu Muokkaa-nappi?
Anneli: mene muokkaamaan sellaista maksutyyppiä, jossa on Muokkaa-nappi. Sitten muuta url-osoitetta korvaamalla maksutyypin tunnus sillä tunnuksella, jota haluat muokata ja paina Enter. Muokkaa kuvausta ja tallenna.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-46-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 45 muistio

Aika: 7.11.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Irina Halminen (Vaara), Leena Kinnunen, Pia Kusmin (Lappi), Iina Niemi (Vaski), Reetta Pihlaja (Siilinjärvi), Kati Sillgren (Helle), Piia Semenoff (OUTI), Hanna Ikonen (Lumme)

* Kehitysehdotus: pitäisikö virkailijatilin voimassaoloajan muokkaamista rajoittaa siten, että kaikki eivät pääsisi muokkaamaan oman tilinsä voimassaoloaikaa (Päivi/Vaara) Lisäys: tästä onkin vanha tiketti Redminessä https://tiketti.koha-suomi.fi/issues/3915
Päätös: Päivi tekee tiketin GitHubiin ja laittaa sen kehittäjien esityslistalle ja asiantuntijaryhmä voi käsitellä tiketin
* Tämän viikon päivitykset ajettu aamulla ja ajo onnistunut

Pohjoisesta etelään

**Vaara**
* ei mitään erityistä, siivottu vanhoja tikettejä ym.

**Lappi**
* Hankintaportaalista on mennyt Kirjastopalvelulle viime maaliskuussa tilaus 5 kpl:sta  nimekettä, mutta KP on virheellisesti palauttanut viestin portaaliin ja tilaus on mennyt KP:n järjestelmään tuplana. Sekä Hankintaportaali että Koha näyttää, että tilauksia on vain 5 kpl.
* Muutoin rauhallista

**Vaski**
* ATK-ihmisten kokoontumisajot Turussa 25-26.4.2024. Ohjelmaa suunnitellaan
* Vaskissa työn alla niteiden erikoistilojen siivous

**Siilinjärvi**
* En ollutkaan tehnyt EXPIRED-maksutyyppiä testille, nyt se on myös siellä.
* Redminessä ei pitäisi olla enää Siilin avoimia tikettejä, viimeinenkin siirretty GitHubiin.

**OUTI**
* TäTin proxy error-tiketti tehty: https://github.com/KohaSuomi/Koha/issues/901
* Vanhentuneiden maksujen -ajon jälkeen tarkisteltu miten maksut ovat mitätöityneet. Vielä menee hetki tutkiessa ovatko ykstityisoikeudelliset mitätöityneet kuten pitääkin.
* Asiakkailta ajossa lähteneiden tekstiviestinumero-täppien korjauksen suunnittelua. Ehdotettu tikettiin voisiko korjausajon suorittaa siten, että tekstiviesti-täpät ajetaan vain asiakkaille, joilla ei ole valittuna noutoilmoitusta sähköpostitse.

**Lumme**
* Perusylläpitoa.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-45-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 44 muistio

Aika: 31.10.2023 klo 9.15 <br />
Läsnä: Anneli Österman, Kodo Korkalo ja Lari Strand (Koha-Suomi), Annika Helastila ja Elina Uotila (Kirkes), Anni Rajala (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Hanna Ikonen (Lumme), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjonimei (OUTI), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Reetta Pihlaja (Siilinjärvi)

* [Viikon 44 päivitys](https://github.com/KohaSuomi/Koha/discussions/875)
* Redminen sulkeminen
  * mukaan RedGraveen ei oteta migraatio-projekteja
  * Redminen sisäiset linkit eivät vielä toimi RedGraven puolella, mutta koitetaan korjata ne myöhemmin.
  * Kodo tekee RedGraven vielä uudelleen, jolloin viimeisimmät muutokset esim. Kehitysehdotusten tiketteihin tulee mukaan
  * Aikataulu: mahdollisimman pian, mielellään jo tällä viikolla.
* Koha-Suomen harjoittelija aloittaa Oulussa ke 1.11.2023
* [Viestiasetusten poistoajossa](https://github.com/KohaSuomi/Koha/issues/391) elokuussa 2023 oli lähtenyt vahingossa pois myös tekstiviestitäppiä, vaikka asiakkaalla oli smsalertnumber. Tämä on todennäköisesti syynä mystisille tekstiviestitäppien katoamisille, mitä osassa kimpoista on raportoitu. Viestitäppiä palautetaan nyt niille asiakkaille, joilla on smsalertnumber. Tässä palautuksessa voi tulla täppiä myös sellaisille asiakkaille, joilla sitä ei ole ollut aiemmin. Kannattaa tiedottaa henkilökunnalle, että täppiä on kadonnut ja niitä voi nyt myös tulla sellaisille asiakkaille, jotka eivät ole sellaista itse valinneet.


Etelästä pohjoiseen

**Vaski**
* Otettu käyttöön sähköposteihin tapa näyttää kirjastokorttitunnuksesta vain kolme viimeistä merkkiä. Jos sikiää asiakaspalautetta, jaetaan tietoa muillekin kimpoille. Mallipohja lisätty [tänne](https://koha-suomi.fi/dokumentaatio/kuititjaviestit/#pohja-jossa-kirjastokorttitunnuksesta-printataan-vain-kolme-viimeist%C3%A4-merkki%C3%A4).
* Vaskissa edetty pidemmän pin-koodin käyttöönoton kanssa. Testailu vielä hiukan kesken, mutta meillä ajateltu että pin-koodi olisi jatkossa 4-10 merkkiä. Kyseltiin pin-koodin generointirimpsusta ja sovittiin, että pidetään rimpsut kimpoissa samanlaisina eikä tehdä toistaiseksi muutoksia generoitavan pin-koodin pituuteen koska kenttään on mahdollista kuitenkin kirjoittaa pidempi pin-koodi. Vaskissa jatketaan hiljaista käyttöönottoa ja kerrotaan, kun kaikki saatu testattua ja otettun pidempi pin-koodi "virallisesti" käyttöön.

**Lappi**
* Edelleen selvitellään maksujuttuja (mitätöinnit, jne.)
* Rovaniemen pääkirjasto muuttaa väistötiloihin 1.4.2024 - 31.3.2025 väliseksi ajaksi. Suunnitelmia muutoksiin aloitellaan.
* Hinta voimassa alkaen -kenttä on nyt piilotettu kaikista marc-pohjista.

**Lumme**
* Tehtiin korjausajo asiakkaille, joilta oli viestitäpät tipahtaneet viestiasetusten poistoajossa.
* Korjausajossa poistettiin asiakastiedoista tieto asiakkaiden sukupuolesta.
* Siivottu ja päivitetty raporttikirjastoa.
* Selvitetty vanhentuneiden maksujen koodeja, jotka ovat tulleet konversiossa.
* Mietitään kimppakohtaista säilytysaikaa asiakastiedoille.

**OUTI**
* OUTIin testille Lari ajoi vanhentuneiden maksujen mitätöintiajon. Julkisoikeudellisten maksujen osalta ajo näytti menneen ok., mutta yksityisoikeudelliset maksut, jotka olivat vanhentuneet tänä vuonna, eivät olleet mitätöityneet. Lari korjaa skriptiä ja ajaa mitätöinnit uudelleen.
* Oulun luetteloinnista tuli eilen tieto, että viime aikoina TäTissä on alkanut tulla proxy erroria. Eilen viimeksi klo 12.43, kun äänitteen oletuspohja oli vaihdettu osakohdepohjaan. Samaan aikaan taustalla oli ollut poistoajo TäTissä? Olisikohan voinut johtua siitä? Pirkko-Liisa tekee tiketin, johon voi kirjata tulevia TäTin proxy erroreita, jos niitä tulee.
* Oulun kaupungin kaikki palvelimet siirtyvät Istekille, kirjaston Ceepos-palvelin siirtyy la-su-välisenä yönä 18.-19.11.2023. Mikään ei pitäisi muuttua eli esim. ip-osoite tai porttimääritykset. Nähtäväksi jää, toimiiko Oulun Ceeposit muutoksen jälkeen. :D
* Vaalan kirjaston Ceepos-palvelin siirtyy CPU:lle 22.11.2023. Tiketti: https://github.com/KohaSuomi/Koha/issues/860

**Kyyti**
* Kyyti-Finnassa on nidetilojen priorisointi tehty tuotantoon Vaskin ohjeiden mukaisesti.

**Siilinjärvi**
* Ei raportoitavaa.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-44-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 43 muistio

Aika: 24.10.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Auli Rantasalo (Vaara), Pirkko-Liisa Lauhikari ja Piia Semenoff (OUTI), Anneli Österman ja Emmi Takkinen (Koha-Suomi), Annika Helastila, Elina Uotila ja Erika Miettinen (Kirkes), Hanna Ikonen (Lumme), Pia Kusmin (Lappi), Reetta Pihlaja (Siilinjärvi), Kati Sillgren (Helle), Susanna Sandell (Vaski), Roosa Väisänen (Kyyti)

* [Viikon 43 päivitys](https://github.com/KohaSuomi/Koha/discussions/856)
* [Koha-seminaariin ohjelma ja ilmoittautuminen](https://github.com/KohaSuomi/Koha/discussions/850)
* [Finna-kehitysehdotuspalaverin tulokset](https://github.com/KohaSuomi/Finna-kehitysehdotukset/wiki)
  * kirjataan esityslistalle ennakkoon, mitkä Finna-ehdotukset käydään läpi kyseisessä viikkopalaverissa.

Pohjoisesta etelään

**Vaara**
* Testattu Vaaran testillä vanhentuneiden maksujen mitätöintiä, joka näyttäisi toimivan kunte pitääkin eri maksutyypeillä.
* TäTissä siivottu pois osa vanhoja tietueita, jotka tuotu vuonna 2014 BTJ:ltä. Paljon siivottavaa vielä riittää, vie aina muutaman minuutin kun käsittelee 1000 nimekettä kerrallaan eräpoistossa. Muutama muukin Koha-Suomen kuvailuryhmästä lupautunut mukaan siivousoperaatioon.
* Irina Halminen ja Päivi käyvät läpi Redminen vanhoja Finna-kehitysehdotuksia ja siirretään toimenpiteitä tarvitsevat tiketit GitHubiin oikeaksi tiketiksi.
* Koska Ceepos saatiin toimimaan viime viikolla, Auli on aloittanut ohjeen päivittämisen. Valmistunee lähiaikoina.

**OUTI**
* Koha-Ceepos-maksurajapinta on saatu toimimaan kaikissa OUTIn Ceepos-kirjastoissa Koha-Suomen konesalimuutosten ja Oulunkaaren kuntien (Ii, Pudasjärvi ja Utajärvi) Ceepos-palvelinten muutosten jäljiltä.
* Koha-jumi torstaina 19.10. klo 9.37, jonka aiheutti tietokantataulun lukkiutuminen.
* OUTIssa otettu käyttöön ke 18.10. järjestelmäasetus AllowRenewalIfOtherItemsAvailable, joka mahdollistaa nyt lainan uusimisen teokseen, josta on varaus, jos tietueessa on muita niteitä, jotka voivat täyttää varauksen.
  ** Käyttäjiltä ei ole tullut valituksia, että toiminnon käyttöönotto olisi aiheuttanut ongelmaa Finnassa tai Kohassa.
  ** Siikajoen neljässä pienessä kirjastossa, jotka eivät ole varuksen noutopaikkoja, aiheutti asetusmuutos sen, että siellä ovat tähän asti pystyneet uusimaan lainoja, vaikka niistä on ollut varauksia. Nyt jos tietueessa ei ole yhtään nidettä saatavana, joka voisi täyttää varauksen, näissäkään kirjastoissa ei voi enää uusia varattuja aineistoja. Kirjastojen niteillä on nidetilana ”Saatavana, ei varattavissa”.
* Kehitystoive: Uusinnan eräpäivä -kohdalle valinta "Muista istunnolle". Tästä oli tehty jo aiemmin kehitysehdotus: https://github.com/KohaSuomi/Koha/issues/305

**Kirkes**
* OKM-tilastointi ja laskutus edelleen selvityksessä.
* Yritetty myös selvittää, mitä yksityisoikeudellisia maksuja Kirkes-kirjastoissa on.
* Käyty läpi Kohassa valmiina olleita tallennettuja raportteja, tavoitteena poistaa sellaiset, mitä ei tarvita.
* Annika ja Elina ovat jatkossa Kirkes-kimpan pääkäyttäjiä ja osallistuvat pääkäyttäjäpalavereihin. Lisäksi Kirkes-kirjastoissa on nyt saatu selvennettyä kuntien pääkäyttäjien roolia ja täten vähennetään superlibrarian-oikeudet kahdelle kimpan pääkäyttäjälle.
* Tuusulaan tullut uusi automaatti, eli ensimmäistä kertaa Koha-tuotantokäyttöaikana tehty tunnukset uudelle automaatille.
* Erika jää tämän viikon jälkeen vuodeksi opintovapaalle ja palaa takaisin marraskuun 2024 alussa. Erikan puolesta kiitos kaikille muille Koha-kirjastojen pääkäyttäjille Kirkes-kirjastojen saamasta moninaisesta avusta ja hyvästä yhteistyöstä käyttöönottoprojektin aikana!

**Lumme**
* Lumpeissa otettiin viime viikolla käyttöön AllowRenewalIfOtherItemsAvailable-asetus, joka laittoi Damaged-tilan alla olevat "Lainattavissa, ei varattavissa" -tilassa olevat niteet varausjonoon, jolloin niteiden uusiminen estyi. Asetus otettiin pois käytöstä ja katsotaan, onko tätä ongelmaa mahdollista kiertää muuta kautta.
* Tuli ilmi tapaus, jossa asiakkaalta oli kadonneet viestitäpät. Asiakas oli saanut elokuun puoleen väliin asti viestit varauksista tekstiviestitse, tämän jälkeen kirjeenä.

**Lappi**
* Normaalia ylläpitoa
* Pähkäilyä: Uudelle asiakkaalle voi tallentaa viestiasetuksia, vaikka hänelle ei samalla tallennakaan puhelinnumeroa tai sähköpostiosoitetta. Jos menee muokkaamaan, Kohassa tulee ilmoitus puuttuvista tiedoista ja valitut viestiasetukset poistuvat. Testillä asetukset poistuvat jo ensimmäisellä tallennuskerralla. Hellessä toimii näin myös tuotannossa. Onko vika IntranetUserJS-rimpsussa? Selvitettävä.

**Siilinjärvi**
* Ei mainittavaa
* Tuotu myös meiltä koemielessä pari asiakkaalta tullutta [Finna-kehitysehdotusta](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues) #11 ja #12

**Helle**
* Tiedotettu Kohan tietoturvaohjeesta ja pyydetty vaihtamaan Koha-salasanat.
* Otettu käyttöön Vaski-kimpan Valuneet tietueet -raportti.

**Vaski**
* Sovittiin, että tehdään tiketti tekstiviestivalinnan estämisestä noutomuistutukselta (https://github.com/KohaSuomi/Koha/issues/861)

**Kyyti**
* Kotkassa ollut useampi tapaus, jossa asiakkaalle on koitettu lisätä puhelinnumeroa matkapuhelinnumero-kenttään ja asiakastiedot tallentaessa matkapuhelinnumero-kenttään tallennettu puhelinnumero ei tallennu asiakkaan viestiasetuksiin tekstiviesti numeroon -kenttään. Ainakin osassa tapauksissa puhelinnumero on ollut jo tallennettuna matkapuhelinnumero-kentässä, mutta jostain syystä se ei ole tallentunut tekstiviesti numeroon -kenttään. Yhdessä tapauksessa asiakkaalle oli mennyt aikaisemmin viestit tekstiviestillä ja yhtäkkiä asiakas olikin saanut kirjeellä viestin joka aikaisemmin oli tullut tekstiviestinä, koska puhelinnumero oli kadonnut viestiasetuksista. Viimeisimmässä tapauksessa puolestaan asiakkaan viestit olivat menneet aikaisemmin sähköpostilla, mutta nyt asiakas halusikin vaihtaa viestinsä tulemaan tekstiviestillä ja kun virkailija koitti tallentaa asiakkaalle puhelinnumeron ei hän saanut sitä tallentumaan tekstiviesti numeroon -kenttään. Tässä tapauksessa en ole varma oliko asiakkaalla ollut aikaisemmin asiakastiedoissaan tallennettuna mitään puhelinnumeroa.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-43-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 42 muistio

Aika: 17.10.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Irina Halminen (Vaara), Reetta Pihlaja (Siilinjärvi), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Roosa Väisänen (Kyyti), Kati Sillgren (Helle), Annika Helastila, Erika Miettinen ja Elina Uotila (Kirkes), Mikko Liimatainen (Vaski), Hanna Ikonen (Lumme), Leena Kinnunen, Pia Kusmin (Lappi)

* Timmi-tilanvarausjärjestelmään ollaan mahdollisesti luomassa yhteyttä Kohaan käyttäen borrowers/status-endpointia. Jos kiinnostusta tämän käyttöönottoon löytyy, yhteyttä voi ottaa Jani Asiakaiseen (jani.asikainen@timmi.fi). /Emmi
* MARCOrgCode-järjestelmäasetukseen pitää laittaa ISIL-koodi, jotta mm. OKM-tilastojen biblio_data_elements-taulujen ajot ei kaadu.
* [Viikon 42 päivitys](https://github.com/KohaSuomi/Koha/discussions/837)
* Koha-seminaari ti 28.11.2023 klo 10-16 Keravalla. Tarkempia tietoja tulossa.
* Finna-palaveri to 19.10. klo 9.15
* [Asiantuntijaryhmän muistio 7/23](https://koha-suomi.fi/asiantuntijaryhma2023)

Etelästä pohjoiseen

**Kyyti**
* uusilla ohjeilla tehdyt Kohan virkailijatunnukset todettiin toimiviksi ja on alettu muuttaa henkilökunnan tunnuksia ohjetta vastaaviksi.
* Kotkassa tehty uusi nidetyyppi 14ELYHYTL (14 ei maksuja, lyhytlainat). Kotkassa nidetyyppiä testataan alkuun lasten uusilla joulukirjoilla. Kokeilu päättyy 31.5.2024 jonka jälkeen päätetään jätetäänkö uusi nidetyyppi käyttöön, vai poistetaanko se. 

**Vaara**
* ei erityistä mainittavaa ylläpidossa
* tehty viime viikolla muutama Finna-kehitysehdotus https://github.com/KohaSuomi/Finna-kehitysehdotukset/ yhdessä pohdittavaksi, ovatko tarpeen vai ei
* Joensuun pääkirjaston Ceepos-kassa ei toimi viime viikon huoltoikkunan jälkeen.

**Siilinjärvi**
* Asiakkaat eivät ole saaneet lisättyä kirjastokorttiaan Siilinjärvi-kuntasovellukseen. Johannan mukaan toimittajalla (Hion Digital) on asetuksissa vanhentunut rajapinta endpoint.
* Vanhentuneiden maksujen tutkinta [#804](https://github.com/KohaSuomi/Koha/issues/804) on loppusuoralla. Maksujen mitätöinti otetaan kiitollisuudella vastaan!
* TAKAAJA-asiakastyypille on jäänyt voimassaoloajaksi 36 kk, ehkä vahingossa. Näitä on nyt myös vanhentunut, mutta vanhenemisesta ei kai sinänsä ole huollettavalle haittaa. Muutetaan uusille voimassaoloajaksi 120 kk ja korjaillaan vanhoja, pitäisi onnistua asiakkaiden erämuokkauksella.
* MARCOrgCode:ssa olikin jo FI-Siili.

**OUTI**
* Koha-Ceepos maksurajapinta ei toimi. Rajapinta lakkasi toimimasta, kun ke 11.10. huoltoikkunan yhteydessä tehtiin palvelinmuutoksia.'

**Helle**
* Helle-sähköpostissa on ollut keskiviikkona (11.10.2023) 114 Kohan asiakasviestiä tiedolla 'toimitus viivästynyt'. Liittynevät Office 365/Outlook-sähköpostipalvelussa tuolloin ilmenneeseen ongelmaan. https://www.reddit.com/media?url=https%3A%2F%2Fpreview.redd.it%2Fanyone-else-seeing-outlook-mail-delivery-problems-in-au-v0-ihfw86mpnjtb1.jpeg%3Fwidth%3D1440%26format%3Dpjpg%26auto%3Dwebp%26s%3D858e6948b23e29b24167639b75fb071a47bc1cff

**Kirkes**
* Hankintaportaali on saatu testattua ja on nyt tuotantokäytössä.
* Laskutusta ja OKM-tilastoja selvitetään vielä.
* Tänään iltapäivällä palaveri Lastu-kirjastojen kanssa, jaetaan Kirkes-Koha-käyttöönottokokemuksia.
* Erika jää marraskuun alusta vuodeksi opintovapaalle, Elina ja Annika jatkavat Kirkes-pääkäyttäjinä. Mietitään vielä pääkäyttäjien työnjako ja henkilökunnan oikeudet järjestelmässä kohdalleen.

**Vaski**
* Käyty läpi vaskissa tulleita kehitysehdotuksia
  * Saatavilla oleviin niteisiin rajaaminen toimimaan oikein asiaan löytyi jo tiketti 359. Lisätty tikettiin tieto bugzillan tiketistä 7012.
  * Vanhentuneille erääntyneille varauksille toivottaisiin asetettavaksi esimerkiksi erikoistila käsiteltävänä, jotta niteet eivät näkyisi hyllyssä tilaisina ennen kuin niteet on saatu käsiteltyä. Tehdään tiketti asiasta.
  * Tärppäämättömien varausten määrää toivottu näkyville tietueen näkymään. Ei totetuteta, sillä tarve ei ole suuri ja toiminnon saa tehtyä raportilla.
 
  **Lumme**
  * Otettiin käyttöön AllowRenewalIfOtherItemsAvailable-asetus.
  * Muuten normaalia ylläpitoa.
 
  **Lappi**
  * Kemistä kyselty Kuntamalli Raindancen yhteyttä Kohaan
  
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-42-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 41 muistio

Aika: 11.10.2023 klo 10 <br />
Läsnä: Anni Rajala (Vaski), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Anneli Österman, Kodo Korkalo ja Lari Strand (Koha-Suomi), Kati Sillgren (Helle), Pirkko-Liisa Lauhikari (OUTI), Erika Miettinen ja Annika Helastila (Kirkes), Maria Joona ja Leena Kinnunen (Lappi), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti)

**Yhteiset**

* Käytäntöehdotus: Vaskilaiset huomasivat lisätä Elementissä/Matrixissa näyttönimeen, kun ovat lomalla. Otetaanko sama tapa yleiseksi käytännöksi kaikille? Esim. ```Anneli Österman | Lomalla 1.10.-3.10.2023```
  * Päätös: Otetaan käytäntöön.
* [Viikon 41 päivitys](https://github.com/KohaSuomi/Koha/discussions/822) piti sisällään vain liitännäisten päivityksiä, koska ns. buildien tekeminen (Koha-Suomen ominaisuuksien liittäminen yhteisön Kohan päälle) ei onnistu tällä hetkellä tiedostojärjestelmän tallennuksessa olevan suorituskykyongelman vuoksi.
* [Huoltoikkuna 11.10.2023](https://github.com/KohaSuomi/Koha/discussions/821)
* Keskusteltiin [vanhentuneiden maksujen mitätöinnistä](https://github.com/KohaSuomi/Koha/issues/804) ja siihen liittyvistä huomioitavista asioista. Siirrettiin lokakuun loppuun määräaikaa, mihin mennessä pitäisi kimpoissa selvittää omat maksut ja miten niille saa käydä (esim. laskutetut, perinnässä olevat yms.).
* Perjantaina 13.10.2023 klo 13-15 on ensimmäinen Bugi-perjantai ja sitä varten Anneli, Emmi ja Lari on kerännyt [Bugiton](https://github.com/KohaSuomi/Bugiton)-tietovarantoon Needs sign off -tilaisia tikettejä yhteisön Bugzillasta.
* Kodo (ja Anneli) pohtivat, miten Redminen tiketit saataisiin talteen haettavassa muodossa ja sen pohjalta on nyt luotu [RedGrave](https://github.com/KohaSuomi/RedGrave)-tietovaranto, johon tikettien tiedot suunnitellaan vietävän markdown-muotoisina tiedostoina. Ne ovat haettavissa tietovarannon yläreunassa olevalla hakutoiminnolla.

Pohjoisesta etelään

**Lappi**
* Kysyttiin asiakkaan muutospyyntöjen automaattisesta hyväksymisestä. Olisi ongelmallista mm. asiakkaan tietosuojan ja tietojen eheyden säilymisen kannalta, eikä teknisesti edes mahdollista ottaa kimppakohtaisesti käyttöön.

**Vaski**
* Kysyttiin konversiomaksujen muutosajon testauksesta. Ei mahdollisuutta saada testikantaa, jossa maksut olisivat anonymisoimatta, joten mietittävä tehdäänkö tuotantoon vai jätetäänkö kokonaan tekemättä.
* Testataan uutta erikoistilaa [tiketissä 799](https://github.com/KohaSuomi/Koha/issues/799) kuvatulla tavalla. Vaski kommentoi tikettiin testaustulokset.

**Vaara**
* Nidetyyppien haku ei onnistu suoraan tarkennetussa haussa, koska indeksointi on väärin. Indeksointi menee perustettavan työryhmän tehtäväksi (teen tiketin asiasta).
* Vaarassa on tullut muutamia Finnan kehitysehdotuksia, jotka lisätään tikettiin https://github.com/KohaSuomi/Finna-kehitysehdotukset
* Vaaran maksuja koskevat maksutyypit käyty läpi ja otettu esimerkit ylös testiajon jälkeen tarkistettavaksi. Vaarassa ei saa poistaa ODUEC-tyyppisiä maksuja (lasku).
* Palautusautomaatti Joensuun pääkirjastossa (ja muut tunneloidut automaatit) eivät toimineet huoltokatkon jälkeen. Osoitemuutos tehtiin Bittigurun päässä, ei automaateilla.

**Helle**
* Kysytty palaverissa, saisiko asiakashakuun tarkan haun. Saatu tieto, että yhteisön Bugzillassa on tuohon liityen tiketti.
* Porvoon tunneloidun palautusautomaatin tämän aamuinen IP-osoitemuutos: automaatti lajitteli palautetut niteet miten sattuu. Automaatin uudelleenkäynnistyksen jälkeen lajittelukin alkoi toimimaan. Joitain yksittäisiä väärinlajitteluja edelleen on kuten on ollut aiemminkin.
* Helle-kirjastojen, Woima-Virran, Kirjavälityksen ja Kirjastopalvelun keskustelutilaisuudessa 4.10.2023 oli mainittu Kohaankin liittyvä toive: portaalissa näkyisi, jos teos on jo Helle-Kohassa.

**OUTI**
* Oulun luetteloinnista on tullut tieto, että jostakin syystä TäTi on alkanut aina välillä heittämään virhettä 500, kun tallentaa tietuetta. Näitä ilmenee aina epäsäännöllisin väliajoin. Toiset käyttäjät olivat valitelleet Kohan hitautta samaan aikaan. Voisiko liittyä siihen? Ongelman ilmoittajaa on pyydetty seuraavalla kerralla ottamaan tarkan ajankohdan ylös ja tiedon siitä, mitä tietuetta oli ollut tallentamassa virheen ilmaannuttua.
* OUTIn verkkomaksamisessa alkoi perjantaina 6.10. erikoinen ongelma. Ceeposin verkkomaksuportaali pyysi maksajaa vahvistamaan aina uudestaan ja uudestaan sähköpostiosoitteensa, eikä maksaja päässyt siirtymään Paytrailin maksusivulle. Eli vaikka s-postiosoitteen antoi pyydettyyn kenttään ja osoite näkyi myös Ceeposin verkkomaksuportaalin maksuerittely-sivulla, Siirry maksamaan -toiminto meni aina sivulle, jossa pyydettiin s-postiosoitteen vahvistamista. Ongelma oli poistunut viikonlopun aikana. CPU ja Paytrail tutkivat ongelman aiheuttajaa.
* Uuden asiakkaan tallennustilanteessa, jos varaustunnus on jo käytössä, tulee siitä ilmoitus, mutta samalla poistuvat valitut viestiasetukset. Tehdään tiketti.
* Jos tulee ihmettelyä, että asiakkaalle on ilmestynyt lainoja, joiden laina ja eräpäivä on menneisyydessä, kannattaa epäillä offline-lainausta. Oulussa oli yhdessä kirjastossa siirretty vahingossa vanha offline-lainatiedosto Kohaan, josta syystä asiakkaille, joiden lainoja oli tiedostossa, oli mennyt lainaan yli vuoden vanhoja lainoja. Ainut hyvä puoli asiassa oli, että tiedostossa ei ollut kuin 5 lainaa. Aiheutti siivottavaa, koska asiakkaille oli ehtinyt tulla vanhoista lainoista maksimimäärä myöhästymismaksuja ja lainassa olleita lainoja siirtyi väärille asiakkaille lainaan.

**Kirkes**
* Hankintaportaali ollut testauksessa ja saadaan toivon mukaan tuotantoon tällä viikolla.

**Lumme**
* Pieksämäen kirjastoautossa Koha jäätyy totaalisesti lehtivarausten yhteydessä. Muuten toimii normaalisti. Pohdittiin, että ongelma johtuu mahdollisesti mobiiliverkkoyhteyksistä. Pyydettiin vielä lisätietoja ja ongelman seurantaa auton työntekijöiltä.
* Muuten normaalia ylläpitoa.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-41-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 40 muistio

Aika: 3.10.2023 klo 9.15 <br />
Läsnä: Pia Kusmin (Lappi), Anni Rajala (Vaski), Päivi Knuutinen ja Irina Halminen (Vaara), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Annika Helastila, Elina Uotila ja Erika Miettinen (Kirkes), Tuomas Kunttu (Kyyti), Reetta Pihlaja (Siilinjärvi), Anneli Österman, Emmi Takkinen ja Kodo Korkalo (Koha-Suomi), Katja Valjakka (Lumme), Kati Sillgren (Helle) 

**Yhteiset**
* vkon 41 palaverin siirto Koha-Suomen kriisiharjoituksen vuoksi keskiviikolle/muulle päivälle?
  * siirretään ke 11.10.2023 klo 10-11 
* api-avaimien teko ja jako jatkossa Koha-Suomessa - ei enää pääkäyttäjien kautta. Perusteena on, että Koha-Suomen pitää tietää, mihin kaikkialle järjestelmä on yhdistetty ja minkälaista kuormaa ne aiheuttavat. Ks. asiantuntijaryhmän muistio palvelujen liittämisestä Kohaan.
  * jatkossa joko pääkäyttäjät pyytävät Koha-Suomea tekemään avaimet tai jos pyyntö tulee suoraan Koha-Suomelle, laitetaan viestin ensin pääkäyttäjille, jotta voidaan varmistaa pyynnön asianmukaisuus. 
* cineast.fi palvelu liitetään Kohaan borrowers/status-endpointilla.
  * borrowers/status-endpoint ei vaadi api-avainta
  * Koha-Suomi toimittaa tarvittavat REST-osoitteet toimittajalle (myös muiden toimittajien/palvelujen osalta sama käytäntö)
* testien redusointipalaveri, ketä kiinnostaisi osallistua ja miettiä, mitä tietoja testeille tarvitaan mukaan?
  * Päivi, Pirkko-Liisa, Vellu, Piia, Hanna, Mikko, Reetta, Leena/Pia, Kati, Tuomas.
  * Anneli kyselee sopivia aikoja Pasilta ja Lasselta ja ehdotetaan sitten niitä osallistujille.
* Vanhentuneet maksut - julkisoikeudelliset ja yksityisoikeudelliset maksut ja niiden vanhenemisaika.
  * julkisoikeudelliset maksut viisi vuotta - vanhenevat/poistetaan vanhenemisvuotta seuraavan vuoden vaihteessa
    * julkisoikeudellisia ovat: myöhästymismaksu (OVERDUE), palautuskehotus (ODUE) ja noutamaton varaus (RESERVE_EXPIRED)
  * yksityisoikeudelliset maksut kolme vuotta - vanhenevat poistetaan päivittäin
* Viikon 40 päivitys
* [Bugi-perjantait alkavat 13.10.2023 klo 13-15](https://github.com/KohaSuomi/Koha/discussions/806)
* [Takaajattomat taattavat](https://github.com/KohaSuomi/Koha/discussions/802)
* Viedään asiantuntijaryhmään ehdotus, että indeksejä ja hakunäyttöihin liittyviä muutoksia varten perustetaan tiedonhakutyöryhmä, joka käsittelee jatkossa niihin liittyvät kehitysehdotukset. Ryhmään kutsutaan tiedonhaun ja kuvailun asiantuntijoita.
  * Katsotaanko Koha-kirjastoissa tarpeelliseksi tehdä kehitysehdotus, jossa 257a (tuontantomaa), 370g (luontipaikka), 382a, b, d, p (esityskokoonpano), 385a (kohderyhmä). 386a (tekijän ominaisuudet), 388a (luontiaika) -kentistä tai joistakin niistä tehtäisiin hakukelpoisia joko hakulinkkinä Perustiedot- näytölle tai hakurajauksena Tarkkaan hakuun?
  * Katsotaanko Koha-kirjastoissa tarpeelliseksi pyytää säätöä tietueen Perustiedot-näytölle siten, että siinä näkyisi tarvittaessa myös 386m- ja a-kentät otsikolla ”Tekijän ominaisuudet” samaan tapaan kuin siellä nyt näkyy 385m- ja a-kenttien tiedot?
* Ajojärjestysmuutos lokakuun huoltoikkunassa
  * Kaikki neljä edustapalvelinta ovat tuotantojen kannalta "kriittisiä" koko ajan, koska jokaisella niistä ajetaan tällä hetkellä Koha-tuotantoja. Esimerkiksi huoltotöiden tekeminen täytyy tästä syystä keskittää pelkästään kahden tunnin kuukausittaiseen huoltoikkunaan ja kaikki huollot on saatava tehtyä ikkunassa. Ikkuna on huoltojen kannalta lyhyt, eikä varmuusmarginaalia juurikaan ole.
  * Seuraavassa huoltoikkunassa ajojärjestystä muutetaan siten että neljästä edustapalvelimesta kaksi kerrallaan ajavat Koha-tuotantoja ja kaksi muuta ajavat testejä, nextejä ym "toissijaisia" Koha-asennuksia ja palveluita. Tällä tavalla tarvittavat huoltotoimenpiteet voidaan tehdä "toissijaisia" palveluita ajaville palvelimille jo ennen huoltoikkunaa. Huoltoikkunassa kriittiset palvelut siirretään jo huolletuille palvelimille ja vasta sen jälkeen otetaan työn alle kahden muun palvelimen huollot. Näille jäljemmin huolletuille palvelimille sitten käynnistetään vuorostaan nuo "toissijaiset" palvelut, kunhan huollot on saatu tehtyä.
  * Tällä tavalla huollot voidaan toteuttaa porrastetusti ja testata rauhassa ja kiireettä. Myös huolloista aiheutuva tuotantokäytössä olevien Koha-installaatioiden alhaallaoloaika lyhenee pääsääntöisesti enintään muutamiin minuutteihin.
  * Miinuspuolena on tunneloitujen automaattien kanssa toimiminen. Kohan siirtyessä palvelimelta toiselle täytyy uuden palvelimen IP osoite käydä muuttamassa automaatin asetuksiin. Tunneloituja automaatteja on kuitenkin Koha-Suomen noin 700 automaatista vain 3-4 ja nekin ovat melko käyttöikänsä päässä. IP-osoitteen mahdollisesta muutoksesta tiedotetaan huoltotiedotteen yhteydessä.
  * Jokaisen kuun toinen keskiviikko klo 7-9 pidetään edelleen huoltoikkunalle varattuna aikana eikä esimerkiksi ajastettuja ajoja ajeta tänä aikana.
  * Muutos on käynyt asiantuntijaryhmässä 28.9. ja se hyväksyttiin yksimielisesti. Katkon lyhyyttä pidettiin muutaman vanhan automaatin vaatimaa lisätyötä merkittävämpänä asiana.

Etelästä pohjoiseen

**Vaski**
* Virheilmoituksia tiedonhaussa, ilmeisesti normaalia enemmän tänä aamuna. Tiketti [#786](https://github.com/KohaSuomi/Koha/issues/786).
* Kellutuksen hallintajärjestelmä -projekti startattu eilen, Koha-Suomen kanssa etsiskellään seuraavaksi palaveriaika.
* Musiikki cd-levyjen kellutus vakiintuu normaaliksi käytännöksi Vaskissa ja kellutus laajennetaan seuraavaksi elokuvatallenteisiin.
* Cineast-palvelua haluttaisiin mahdollisesti päästä testaamaan jo lokakuussa. Vaski laittaa Koha-Suomen support-postiin pyyntöä, kun tarvetta saada homma etenemään.

**Kirkes**
* Edelleen konversioon liittyviä selvitettäviä asioita. Esimerkiksi laskutus tällä hetkellä selvityksessä.
* Tuusulan kirjastoautossa tullut noudettaville varauksille kahta erilaista viimeistä noutopäivää: osalle tulee auton eräpäiväkalenterin mukainen viimeinen noutopäivä kuten pitääkin, osalle viimeinen noutopäivä vaikuttaa tulevan muiden kirjastoyksiköiden eräpäiväkalenterien mukaan, eli noutoajaksi tulee 7 aukiolopäivää, kun sen pitäisi auton kalenterissa olla 14 aukiolopäivää. Selaimen muistin tyhjentäminen ei ole auttanut. Erika siirtänyt tiketin Kirkes-repositoriosta Koha-repositorioon. Varausten noutopäiviä voi nyt muokata manuaalisesti vastaamaan auton eräpäiväkalenteria.

**Lappi**
* Ensi vuoden tilien ja budjettien läpikäyntiä ja lisäilyä
* Normaalia ylläpitoa

**Vaara**
* Päivi ollut pari viikkoa lomalla, vaatii vielä vähän asioihin paneutumista että pääsee kärryille
* Aamulla soitettiin Joensuun pääkirjaston edellisen illan lainaustilanteesta, jossa asiakas oli tullut noutamaan varaustaan, poiminut sen varaushyllystä, mutta ei voinut lainata automaatilla, kun nide olikin lainassa. Ilmeisesti toiselle asiakkaalle oli lainattu kaksi kirjaa 26.9., joista toinen oli noudettavan niteen viivakoodilla lainattu (onko lukija lukenut väärin vai mistä virhe, en tiedä). Tämän toisen asiakkaan lainoissa oli vielä eri nide kuin mistä hänelle oli lähtenyt noutoilmoitus eli sotkettu oikein perusteellisesti. Täytyy selvittää asiaa hoitaneen virkailijan kanssa.

**OUTI**
* Tullut vastaan taas yksittäinen nide, kun sitä on yrittänyt hakea nidetunnuksella, on tullut virhe 500. Kyseisen tietueen, jossa nide on kiinni, uudelleen tallentaminen on poistanut ongelman.
* Oulun luetteloinnista on tullut nuottiaineiston valutukseen liittyvä korjauspyyntö eli viivalliset ISMN-tunnukset eivät valu TäTistä paikalliskantaan, tiketti: https://github.com/KohaSuomi/Koha/issues/807
* Oulussa oli muutamalle koneelle päivittynyt Firefoxin versio 115+, jossa ilmeni kuittitulostusongelma eli kuitin vasemmasta reunasta jäi puuttumaan noin yhden merkin verran. Ongelma korjaantui, kun vaihdettiin tulostinasetuksiin tulostimen ajureista riippuen kohtaan Reunukset: "Oma (mm)" tai "Mukautettu (tuumina)". Reunukset laitetaan muuten nollaksi, mutta vasen reunus laitetaan arvoon 0,05, jos arvo annetaan tuumina. Jos arvo annetaan millimetreinä, oikea arvo on 1,2. Kuittitulostimissa voi olla hieman eroja, joten jos annetut arvot eivät riitä, voi kokeilla hiukan suurentaa tai pienentää lukuja. Firefoxin selainversiossa 102+ ei ole vastaavaa ongelmaa ilmennyt.
* Taas tullut pari ongelmatapausta, kun Finnassa asiakkaan Omat tiedot -osiossa ei päivity Finna-tilin asetuksen sähköpostikenttä, jos asiakkaan s-postiosoite muuttuu tai se poistetaan Kohasta. Ongelmasta laitettu useamman kerran Finna-tukeen.

**Kyyti**
* Ratkaisimme tiketin [#782](https://github.com/KohaSuomi/Koha/issues/782) ongelman ottamalla asetuksen NoIssuesChargeGuarantees pois päältä

**Siilinjärvi**
* Ei mainittavaa.
* Vanhentuneet maksut [#804](https://github.com/KohaSuomi/Koha/issues/804) vaatii Siilissä vielä perkausta ja pohdintaa.

**Lumme**
* Ei erityistä. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-40-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 39 muistio

Aika: 26.9.2023 klo 9.15 <br />
Läsnä: Susanna Sandell (Vaski), Irina Halminen (Vaara), Piia Semenoff (OUTI), Leena Kinnunen, Pia Kusmin (Lappi), Kati Sillgren (Helle), Annika Helastila (Kirkes), Erika Miettinen (Kirkes), Elina Uotila (Kirkes), Tuomas Kunttu (Kyyti), Roosa Väisänen (Kyyti), Reetta Pihlaja (Siilinjärvi), Katja Valjakka (Lumme)

**Yhteiset**
* [Viikon 39 päivitys](https://github.com/KohaSuomi/Koha/discussions/795)
* [Onko kaikilla kunnossa #572](https://github.com/KohaSuomi/Koha/issues/572)?
* Muistin virkistykseksi: [Tikettien tekeminen ja kommentointi](https://github.com/KohaSuomi/Koha/wiki/Tikettien-tekeminen-ja-kommentointi) sekä [Tietoturvaohjeet](https://koha-suomi.fi/dokumentaatio/tietoturvaohje/)
* "Bugi-perjantait" - milloin aloitetaan?
  * "Bugiton" perjantaina 13.10.2023 klo 13-15

Pohjoisesta etelään

**Vaara**
* Itsepalvelulainaus testataan käännösten osalta Kiihtelysvaarassa.
* Omatoimen käyttökiellon poistuminen automaattisesti asiakkaalla määräajan jälkeen (varmistus).

**Vaski**
* Keskustelua asiakashaun toiminnallisuudesta (Koha avaa suoraan asiakastiedot jos hakutuloksia vain yksi. Haussa toimii katkaisu eli ”virta” -haulla voi hakutulokseksi tulla virtanen. Vaskin mielestä olisi parempi että vain korttinumerolla haettaessa haku veisi suoraan hakutulokseen, muissa hauissa käyttäjä päätyisi aina hakutuloslistaan. Tällä pyrittäisiin vähentämään nimihakuun liittyviä virhemahdollisuuksia. Hakutuloslistaan päätyminen ei saanut kannatusta.
* Olisi hyvä, jos automaatilla voisi lainata jo lainassa olevaa, kuten virkailijaliittymässä (tapahtuu palautus ja lainaus). Yhteisöstä löytyy tästä tiketti: https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=18317. Sovittiin, että Vaski tekee tiketin.
* AVIn lakikoulutuksessa mainittiin, että ” Lainauskielto tulee poistaa kun maksut vanhenevat” Heräteltiin keskustelu maksujen vanhenemisesta Kohassa. Asia siirtyi Koha-Suomen kehittäjien palaveriin
* Vaski siirtyi tänään tuotantoon uuden nidetilojen priorisoinnin osalta Finnan saatavuustiedoissa. Ohjeet priorisoinnin muuttamiseen tulevat tähän tikettiin: https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/2

**OUTI**
* Hankintaosaston pyynnöstä OUTIssa niteiden muokkausnäkymästä vähennetty kenttiä näkyviltä. 
* OUTIssa on vielä kesken Finna-tuen kanssa Muu nimi-kentän näkymään saaminen Finnassa. Se laitetaan näkyville ensin OUTIn testi-Finnaan.
* Pirkko-Liisa oli laittanut Finna-tukeen viestiä, kun väärä PIN-koodin antaminen tuplaa asiakkaan epäonnistuneiden kirjautumisten määrän. Finna-tuki lupasi tutkia ja kyseli Kohan pään plugareista. Viesti välitettiin Koha-kehittäjille.
* Vaalan kirjaston remontti on loppumassa, joten huomenna tehdään 27.9.2023 avaustoimenpiteitä.
* Raahen kokoelmaan on haluttu tilata vain yksi nuotti, mutta Kohassa tietueen tilaustiedoissa näkyy, että nuotteja on tilattu yhteensä 4 kpl. Näyttäisi, että EditX:n kautta on tilattu ensin kolme nidettä ja vajaata viikkoa myöhemmin hankintaportaalin kautta 1 kpl. Edifact-sanomassa tilattujen niteiden määrä näyttää olevan kolme ja hankintaportaalissa näkyy tilausmääränä yksi. Raahelaiset ovat ottaneet yhteyttä Kirjastopalveluun, mutta vielä ei ole sieltä vastausta saatu. Tietue: https://outi.koha-suomi.fi/cgi-bin/koha/catalogue/detail.pl?biblionumber=2311377

**Lappi**
* Konversiossa Origosta Kohaan on yhdestä kirjastosta tullut tietueita, joissa kielikoodit eivät ole standardin mukaisia, vaan avattuna (esim. suomi, tanska). Nämä ovat konversiossa siirtyneet kielikenttiin toistumina esim. suo, mi, tan, ska, ja näkyvät nyt Finnassa erikoisina kielinä, esim. maori. tsimisi.
* Tuplahankintojen selvittelyä edelleen.
* EditX-virheitä, koska ei ole vielä ennätetty tehdä ensi vuoden tilejä

**Helle**
* Yhteisö-asiakastyypin asiakastietojen Etunimi-kenttäarvot kopioitu Sukunimi-kenttään ja Etunimi-kenttäarvot poistettu.

**Kirkes**
* EditX-hankintaan ja laskutukseen liittyvät valmistelut käynnissä. 

**Kyyti**
* Kyytissä on henkilökunnnan käyttöoikeusohje testattavana.
* Kirjastojen videopalvelukilpailutuksen voitti Cineasterna ja valitus markkinaoikeudessa hylättiin, joten syksyn aikana heidän pitää tehdä rajapinta Kohaan. Johanna kertoi, että he ovatkin jo olleet yhteydessä Koha-Suomeen.
* Finnan versiopäivitys-foorumilta napattu:
Kohan REST-pluginiin on nyt tehty korjaus, jotta varausjono laskettaisiin oikein. Tulee siis Kohan puolella voimaan, kun plugini jossain vaiheessa päivitetään vähintään versioon v23.05.03.
https://foorumi.kiwi.fi/t/finnan-versiopaivitykset/437/397
* Kotkassa on otettu käyttöön uudet nidetyypit 14MRAJVAR (14 maksut, rajoitettu varaus) liikuntavälineille ja 28MRAJVAR (28 maksut, rajoitettu varaus) soittimille.

**Siilinjärvi**
* Ei mainittavaa, muut asiat työllistävät taas.

**Lumme**
* Ei mainittavaa.


[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-39-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 38 muistio

Aika: Keskiviikko 20.9.2023 klo 13 <br />
Läsnä: Anni Rajala (Vaski), Pia Kusmin (Lappi), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Reetta Pihlaja (Siilinjärvi), Anneli Österman, Lari Strand ja Pasi Kallinen (Koha-Suomi)

**HUOM!** Eri kokousaika kuin yleensä!

**Yhteiset**
* onko tarvetta tehdä korjausajoja yhteisöasiakkaiden nimiin? Yhteisöasiakkailla ei näy etunimeä, jos asiakastyypin tyyppi on "yhteisö". Näitä ehkä korjailtiin jo edellisen version versionvaihdon jälkeen, mutta onko vielä jossain tarvetta?
  * Näitä voi tutkia esim. sql-kyselyllä ```select borrowernumber, surname, firstname from borrowers where categorycode='YHTEISO' and firstname is not null```
  * sovittiin, että kaikki käyvät läpi oman kimpan yhteisöasiakkaat SQL-kyselyn avulla ja muokkaa tarvittaessa tietoja näkyviin sukunimikenttään. Sen jälkeen etunimikentän voi tyhjentää asiakkaiden erämuokkauksella (HUOM! etunimikentän pakollisuus pitää ottaa pois hetkeksi, jotta ajon saa tehtyä).
  * jos muutettavia on todella paljon, voi tehdä tukipyynnön etunimikentän tyhjentämisestä.
* [Syntymäaikakentän tyhjennys yhteisöasiakkailta](https://github.com/KohaSuomi/Koha/issues/778)
  * poissaolleiden edustajat, käykää kommentoimassa tikettiin, haluatteko tekin ajon.
* [Kausijulkaisun vastaanottoon mahdollisuus viedä nide tarratulostuslistalla](https://github.com/KohaSuomi/Koha/issues/508)
  * toteutus ei ihan yksinkertainen, pohditaan vaihtoehtoja
* Käyttekö läpi kaikki omat tikettinne ja suljetteko ne, jotka eivät ole enää ajankohtaisia.
  * Käykää loputkin tutkimassa [tiketin 572](https://github.com/KohaSuomi/Koha/issues/572) tarve ajolle omassa kimpassa.
*  [Muutoksia viivakoodien generointiin](https://github.com/KohaSuomi/Koha/issues/772)
* [Onko pikahaun tyhjäysruksi vielä tarpeellinen kehitysehdotus](https://github.com/KohaSuomi/Koha/issues/341)?
* [Viikon 38 päivitys](https://github.com/KohaSuomi/Koha/discussions/785)
* [Muu nimi -kenttään muutos nimeen](https://github.com/KohaSuomi/Koha/issues/783)?
* Nextit pystyssä vasta OUTI, Helle, Vaski ja Lappi, koska huoltokatkossa tehty tiedostojen maksimimäärämuutos ei riittänyt/ollut oikea. Määrää säädetään taas lokakuun huoltoikkunassa (11.10.2023), jonka jälkeen saadaan loput nextit ylös. Versionvaihtoa edistetään jo olemassa olevilla nexteillä.


Etelästä pohjoiseen

**Vaski**
* Otettu käyttöön oma not for loan -erikoistila "Uusin numero, luettavissa kirjastossa" lehtien uusimmille numeroille jotta pystyttiin sallimaan varaaminen verkkokirjaston kautta.

**Lappi**
* Kysy Kohasta -session suunnittelua. Pidetään 10.10. ja aiheena on tällä kertaa Hankinta.
* Kaksivaiheinen tunnistuautuminen otettu käyttöön pääkäyttäjätunnuksilla.
* Ensi vuoden hankinnan tilejä tarkistetaan ja päivitetään.
* Yhdellä kirjastolla tuplaniteitä hankinnassa. Ei tuplakoreja niin kuin tavallisesti. Koitetaan selvittää, mistä nämä ovat tulleet. Hankintaportaalissa tilaukset ok.

**OUTI**
* Rajakylän kirjastossa tuli vastaan tapaus, että nide näytti olevan samaan aikaan lainassa ja saatavana. Asiakkaan muutoslokilla eikä niteen tapahtumalokilla näkynyt lainaustapahtumaa. Niteen tapahtumalokilla näkyi edellinen lainaus, jonka oli tehnyt eri asiakas. Tiketti #774. Epänormaalin tilanteen aiheuttajaa ei löytynyt. Niteen arvoksi korjattu lainassa. Vastaava tapaus on ollut myös aiemmin Kyytissä.
* Hoksautettu kirjastoja, että tekevät budjetit ja tilit vuodelle 2024, sillä ainakin OUTIn kirjastoille aineistotoimittajat ovat tehneet jo verkkokauppoihin ostoskorit vuodelle 2024. Jos kirjastot tilaavat näille ostoskoreille, tilaukset eivät siirry Kohaan, koska vastaavia tilejä ei löydy Kohasta ja  EDItX-sanomat päätyvät virheeseen.
* OUTIssa on kilpailutettu kirjastokorttien painatus. Käyttöön tulee kortit, joissa asiakastunnuksen alussa ei ole enää kuntakoodia vaan tunnus alkaa kimpan nimellä OUTI + 7 numeroa.
* Otetaan käyttöön Muu nimi -kenttä asiakkaan kutsumanimelle.
* Lopetetaan ”Tarkista osoite”-täpän käyttö asiakkaan tiedoissa. Jatkossa tieto virheellisestä postiosoitteesta laitetaan "Lisää viesti" -toiminnolla. Näin asiakas ei mene lainauskieltoon virheellisen postiosoitteen vuoksi.
* Ilmeisesti kaikki Oulunkaaren kuntien kirjastojen Ceepos-palvelimet siirtyvät CPU:n palvelimelle lokakuun aikana. Yhteysosoitteen muutospyyntö tullut jo Pudasjärveltä ja Iistä. Teemme tiketit kaikista sitä mukaan kun ne tulevat.

**Kyyti**
* Olen vihdoin päivittämässä Kyytin henkilökunnan käyttöoikeuksia. Pyysin jos jostain kimpasta voisi lähettää omat ohjeet verrattavaksi.
* Tein tiketin [782](https://github.com/KohaSuomi/Koha/issues/782) Automaatti laskee yhteen takaajan ja taattavan maksut

**Siilinjärvi**
* 1.9. käyttöön otettu verkkomaksaminen on lähtenyt sujumaan hyvin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-38-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 37 muistio

Aika: 12.9.2023 klo 9.15 <br />
Läsnä: Iina Niemi (Vaski), Pia Kusmin (Lappi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Kati Sillgren (Helle), Pirkko-Liisa Lauhikari (OUTI), Hanna Ikonen ja Katja Valjakka (Lumme), Anneli Österman ja Lari Strand (Koha-Suomi), Tuomas Kunttu (Kyyti)

**Yhteiset**
* TäTin käyttäjätunnusten yhtenäistäminen?
  * ei muuteta olemassa olevia tunnuksia, jatkossa tehdään ohjeen mukaan
  * laitetaan päälle triggeri, joka kopioi cardnumberin userid-kenttään.
    * otetaan käyttöön viikon 38 päivityksen yhteydessä. Käyttäjät voivat viikon aikana käydä tarkistamassa omat tunnuksensa.
  * mikropalvelun kytköksiin ei tarvitse tehdä muutoksia, mutta jos pääkäyttäjä on tähän mennessä joutunut kirjautumaan userid:llä, pitää jatkossa kirjautua cardnumberilla.
* [viestien arkistointi vuositauluihin tehty kaikkiin kimppoihin](https://github.com/KohaSuomi/Koha/issues/711#issuecomment-1707801721)
  * [Arkistoitujen viestien hakeminen raportilla](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/#arkistoitujen-viestien-hakeminen-message_queuen-vuositaulusta)  
* Ei päivitystä tällä viikolla.
* [Keskiviikkona säännöllinen huoltoikkuna](https://github.com/KohaSuomi/Koha/discussions/766), tiedossa katko, koska palvelimet bootataan, jotta saadaan voimaan isompi tiedostojen maksimimäärä ja nextit voidaan taas käynnistää ja alkaa valmistelemaan versionvaihtoa.

Pohjoisesta etelään

**Vaski**
* Ulkomaalaiset numerot siivottu asiakasrekisteristä
* Tekeillä koodi, jolloin Finnassa Damaged-tilaiset niteet eivät näkyisi punaisella. Kun tulee käyttöön, jaetaan yhteisesti. Odottaa nidetilojen priorisoinnin korjaamista.

**Lappi**
* Normaalia ylläpitoa
* Kysymys/kehitysehdotus: Juuri nyt lainattujen kuitti. Tällä hetkellä kuittiin tulee kaikki päivän aikana lainatut ja uusitut. Muilla kirjastoilla ei ollut tarvetta ko. kuitille. Automaatilta saa yhden lainauskerran lainakuitin. Mietitään vielä, tehdäänkö kehtiysehdotusta vai ei. Bugzillassa tästä on kehitysehdotus 34210.

**Vaara**
* edelleenkin on nimekkeitä, joita ei voi varata verkkokirjaston kautta. 2/10 aikaisemmin toimimattomaksi ilmoitetuista toimii, muut ei. Laitan uuden viestin Kansalliskirjastoon.
* Kuittipohjiin DUEDGST ja PREDUEDGST halutaan näkyviin myös nimekkeen osan numero. Irina tekee tiketin asiasta.

**Helle**
* Asiakastiedon kopioinnnissa ei muodostunut kuluva päiväys uuden asiakastiedon Tullut asiakkaaksi -kenttään. Tiketti nyt tuosta https://github.com/KohaSuomi/Koha/issues/771 . Vastaavasta mainittu myös tiketissä https://github.com/KohaSuomi/Koha/issues/610
* Muistutusviesti noutamattomasta varauksesta - onko viesti varauskohtainen vai meneekö tarvittaessa myös koosteviestinä?

**OUTI**
* Asiakastyyppien muutosajoissa on ollut ongelmia. Ajo, joka muutti ”Lapsi, omatoimi kielletty” -> ”Lapsi, omatoimi sallittu”, kun asiakas on täyttänyt 16 vuotta, ei viime aikoina ole toiminut kaikilta osin. Samoin viivettä on ollut asiakastyypin muutosajossa henkilöasiakkaaksi, kun asiakas on täyttänyt 18 vuotta. Selvisi, että OUTIssa oli yksi lapsiasiakas, jolla ei ole takaajaa ja tämä asiakastietue kaatoi ”Lapsi, omatoimi sallittu” -ajon. Asiakkaalle muutettiin asiakastyyppi manuaalisesti, joka näytti korjaavan ongelman. Henkilöasiakas-ajon siirto eteenpäin on ilmeisesti auttanut tähän ongelmaan.
* Oulun luetteloinnista tuli kysymys, että saisiko Finnassa näkyvien damaged-arvollisten (esim. Saatavana, ei varattavissa) olevien niteiden punaiset ruksit vihreiksi pallukoiksi, kun nide ei ole lainassa. Vaskissa on kehitteillä Finnaan koodi, joka näyttää damaged-arvolliset niteet viherällä tai keltaisella pallukalla, kun nide ei ole lainassa.
* Väärä PIN-koodi Finnassa tuplaa epäonnistuneiden kirjautumisyritysten määrän Kohaan. Finnan ongelma. Tiketti: https://github.com/KohaSuomi/Koha/issues/761. Pirkko-Liisa reklamoi asiasta Finna-tukeen.
* Fiktiivisen hahmon asiasanalinkki ei toimi, jos järjestelmäasetuksessa TraceSubjectSubdivisions on valittuna ”Sisällytä” eli haun pitäisi sisältää myös osakentät. Syyksi selvisi, ettei 600c-kenttä sisälly indeksiin. Viedään tiketti asiantuntijaryhmälle päätettäväksi, lisätäänkö kenttä indeksiin. Tiketti: https://github.com/KohaSuomi/Koha/issues/459
* Kuusamoon on avattu uusi yhtenäiskoulu, johon tulee koulukirjasto. Kirjastoon tulee Mikro-Väylän lainausautomaatti. Koulukirjaston niteet tallennetaan Kuusamon kirjastolle hyllypaikalle Koululukirjasto, hyllytarkenteella ”Nilon yhtenäinen peruskoulu”.
* Pudasjärven kirjaston Ceepos-palvelin vaihtuu 11.10. Tiketti: https://github.com/KohaSuomi/Koha/issues/763
* Oulun luetteloinnista tuli kysymys, että voisiko Tätin luetteloinnin kuvailupohjan 003-kenttään saada marc21_orgcode.pl -liitännäisen käyttöön? Päivi lisää Tätin luettelointipohjiin.
* OUTIlaiset eivät osallistu viikon 38 viikkopalaveriin. Osallistuvat Pohjois-Suomen AVI:n Arjen kirjastojuridiikkaa -koulutukseen.

**Lumme**
* Normaalia ylläpitoa, pienten asioiden selvittelyä.
* Finna kaatui karusellin päivityksen yhteydessä n. tunniksi symlinkkien tarkistusvirheen takia.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-37-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 36 muistio

Aika: 5.9.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Irina Halminen (Vaara), Hanna Ikonen (Lumme), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Leena Kinnunen ja Pia Kusmin (Lappi), Tuomas Kunttu (Kyyti), Kati Sillgren (Helle)

**Yhteiset asiat**
* Ei päivitystä vkolla 36
* Kirkeksen käytöönotto menossa, työllistää ainakin Kodoa ja Annelia. Myös jonkin verran muita.

Etelästä pohjoiseen

**Vaara**
* Eri raporteilla tutkailtu kokoelmatietoja. Havaittu yllättävän paljon kuljetustilaisia niteitä, jotka löytyvät toisen kirjaston
hyllystä. Kehotetaan kirjastoja käyttämään kuljetustilaraportteja apuna näiden niteiden tilojen korjaamiseen. 
Tila jää päälle, kun nide ei menekään kohdekirjastoonsa vaan palautetaan jossain muussa kirjastossa (jossa nide saa kellua).
* Tehty AutoItemtype-asetuksia testikantaan. Ensin pieni otanta asetuksia ja muutokset kuvailupohjiin kenttään 952y. 
Pieni otanta toimi ihan hyvin, tosin ongelmana on tällä hetkellä puuttuva ominaisuus "ei valintaa". Asetusrivejä jo 90 ja lisää tulee
kun ehdin niitä muokata jokaiselle aineistotyypille, hyllypaikalle ja kokoelmakoodille, joita tarvitaan. Onneksi meillä ei ole hyllytarkenne käytössä :)

**Lumme**
* Erinäisiä asioiden selvittelyjä.
* Lumpeisiin ajettiin nyt yhtenäistämisajo kirjastokorttien numeroille ja userID:lle, niin saatiin tietokanta kuntoon. Triggeri näyttää toimivan hyvin.
* Tarkoitus käydä kuittipohjat läpi ja yhtenäistää kaikille kirjastoille yhtenäiset kuitit, jotta virhetilanteiden selvittely helpottuu.

**OUTI**
* OUTIssa on yksi asiakas, jolla syntymäpäivä 3.4.1942. Asiakastietojen avaaminen antaa virheen 500. Päivämäärä on sama kuin Suomessa on testattu kesäaikaan siirtymistä ja perlin DateTime moduulista tällaiset päivämäärät ovat virheellisiä. Korjaus tulee seuraavaan versioon. Asiakkaan syntymäpäivä vaihdettu väliaikaisesti 2.4.1942. Tiketti: https://github.com/KohaSuomi/Koha/issues/624
* Kempeleen liikuntavälinelainaamon itsepalvelulainauksessa tuli timeout 30 min. kuluttua. Lari on tuonut testille kovakoodatun timeoutin automaattitunnukselle. Nyt testien perusteella näyttäisi toimivan. https://github.com/KohaSuomi/Koha/issues/748. Testataan myös, että virkailijatunnusten timeout toimii vielä kuin pitääkin eli 30 min.
* Asiakaspalvelussa on tullut vastaan lapsiasiakas, joka on täyttänyt 16 vuotta 31.8.2023, jolloin hänen asiakastyyppi olisi pitänyt muuttua ”lapsi, omatoimi sallituksi”, mutta muutos tapahtui vasta seuraavan yön ajossa eli 1.9.2023. Testasimme myös, muuttuuko asiakastyyppi "Lapsi, omatoimi sallittu" henkilöasiakkaaksi sinä päivänä, kun hän täyttää 18 vuotta, mutta siinäkin tapauksessa asiakastyypin muutos tapahtui päivän myöhässä. Tiketti: https://github.com/KohaSuomi/Koha/issues/754
* OUTIssa on paljon epäonnistuneita Niteiden poistoja eräajona. Osoittautui, että suurin osa poistossa olleista niteistä ovat olleet siirtolainakokoelmissa, jota OUTIssa käytetään yhdessä kunnassa. Siirtolainakokoelmasta poiston esti vanhasta versiosta jäänyt ”riippuvuus”, joka on nyt poistettu. Poistoeristä löytyi vielä niteitä, jotka ovat yhtä tietokannassa. Tiketti: https://github.com/KohaSuomi/Koha/issues/738. Muutetaan failed-tilassa olevat niteiden eräpoistot uudelleen pending-tilaan ja katsotaan, poistuuko niteet.
* Kimpat, joilla on käytössä Firefoxin versio ESR 100+ ja olette saaneet Kohan kuittitulostukset toimimaan, olisiko mahdollista, että joku teistä lisäisi toimivat asetukset Kohan ohje suomeksi -ohjeeseen -> Kuittitulostuksen asetukset? Oulussa emme ole vielä saaneet uudempaa versiota käyttöön, joten ohjetta ei ole voitu päivittää.
* Pirkko-Liisa tekee kehitysehdotustiketin vanhasta toiveesta, että Finnassa pystyisi järjestämään lainahistoriaa tekijän, nimekkeen ja aineistotyypin mukaan sekä tekemään hakuja omaan lainahistoriaan.

**Lappi**
* Normaalia ylläpitoa
* Kysymys: Voiko kokoelmakoodin tunnusta muuttaa (auktorisoidut arvot - ccode): voi, mutta ei kannata. Ei päivity niihin niteisiin, jossa vanha tunnus on käytössä. Eli muutamme vain koodin nimeä ja kuvausta. 

**Kyyti**
* 1.9. voimaan tulleet maksumuutokset vietiin perjantaina Kohaan. Paitsi laina- ja maksusäännöt myös viestipohjat piti käydä läpi, koska niissäkin on maksuja mainittu.
* Huomattu, että jos auktorisoiduissa arvoissa määrittää kokoelmakoodin vain johonkin kirjastoon, niin muissa kirjastoissa se ei silloin näy niteittein muokkauksessa eikä tarkassa haussa, mutta nidehaussa silti näkyy.

**Helle**
* Asiakastiedossa on Matkapuhelinnumero-arvo mutta ei Tekstiviesti numeroon -arvoa: aiheuttanut haasteita tekstiviestityksen käyttöönotossa. Kehittäjä Lari Strand lisäsi arvottomiin Tekstiviesti numeroon -kenttiin Matkapuhelinnumero-kentän arvon. Tiketti https://github.com/KohaSuomi/Koha/issues/744

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-36-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 35 muistio

Aika: 29.8.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Pirkko-Liisa Lauhikari (OUTI), Iina Niemi (Vaski), Susanna Sandell (Vaski), Reetta Pihlaja (Siilinjärvi), Hanna Ikonen (Lumme), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Leena Kinnunen ja Pia Kusmin (Lappi)

**Yhteiset asiat**
* [Viikon 35 päivitys](https://github.com/KohaSuomi/Koha/discussions/740)
* [Hallituksen tiedote 6/2023](https://koha-suomi.fi/hallituksentiedotteet2023#koha-suomen-hallituksen-tiedote-62023)
  * Koha-seminaari 28.11.2023 Helsingissä

Pohjoisesta etelään

**Vaara**
* Joensuussa ihmeteltiin noutamatonta varausta, josta ei tullut asiakkaalle maksua. Samana päivänä kun asiakkaalle oli 
lähtenyt noutoilmoitus niteestä, hän oli lainannut samasta nimekkeestä toisen niteen (miksi? ei tietoa). Annelin selvityksen
mukaan "action_logsilla näyttäis olevan samaan aikaan kuin lainaus on tehty tuollainen action kuin "FILL". 
Tuossa on voinut käydä niin, että kun hälle on lainattu toinen saman teoksen nide, niin alkuperäinen varaus on "täyttynyt" sillä.
old_reserves-taulussa varaukselle on kirjautunut patron_expiration_date-sarakkeeseen tuo 11.8.2023, jolloin asiakas on lainannut teoksen."
Testausten jälkeen selveni: Jos tietueeseen on yksi tai useampi (hylly)varaus ja asiakas lainaa jonkin hyllyssä olevan niteen, 
vaikka hällä on toinen noudettavissa, niin silloin noudettavissa oleva varaus poistuu.
Mutta jos tietueeseen ei ole muita varauksia ja asiakas lainaa muun niteen kuin noudettavissa olevan, 
niin varaus ei poistu toisen niteen lainatessa.
* Vaaran Finnassa on nimekkeitä, joita ei voi siellä varata. Kansalliskirjaston kanssa asiaa selvitettiin ja siihen tehtiin päivityskorjaus REST-pluginiin. Testauksessa näytti korjaus auttavan, mutta edelleen löytyy nimekkeitä, joiden varaaminen ei onnistu. Selvitellään asiaa uusien esimerkkien avulla.

**OUTI**
* Laskuttajalta tuli tieto, jos laskutustyökalussa painaa vahingossa toimintoa Luo Finvoice/Luo e-lasku kaksi tai useamman kerran, syntyy asiakkaalle aina uusi lasku. Tiketti: https://github.com/KohaSuomi/Koha/issues/734
* OUTIssa on paljon epäonnistuneita Niteiden poisto eräajona -ajoja. Suurimmassa osassa on ollut vain yksi poistettava nide, mutta elokuun alussa on ollut myös kolme erää, joissa jokaisessa on ollut lähemmäs 50 poistettavaa nidettä. Tiketti: https://github.com/KohaSuomi/Koha/issues/738
* Kempeleen kunnan Liikuntalainaamo on aloittelemassa liikuntavälineiden lainaamista Kohan itsepalvelutoiminnolla.
* Iin Kuivaniemen kirjastosta tuli palautetta, ettei kirjaston omatoimilaite päästä sisälle enää lapsiasiakasta, jolla asiakastyyppinä on ”Lapsi, omatoimi sallittu”. Ongelman syy selvinnyt 30.8.: Iissä omatoimi sallitaan nykyisin vain 16 vuotta täyttäneille. Määritys asetettu ovikoneelle. Lapsiasiakas oli alle tämän rajan.

**Vaski**
* Pääkäyttäjillä kaikilla käytössä kaksivaiheinen tunnistautuminen.
* Tänään pidetään palaveri Kansalliskirjaston kanssa nidetilojen priorisoinnista https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/2 
* Vaskissa on syntynyt kaksi tuplaverkkomaksua bugikorjauksen jälkeen

**Siilinjärvi**
* [Tiketti #692](https://github.com/KohaSuomi/Koha/issues/692) kirjastokortin numeron ja käyttäjätunnuksen yhtenäistämisestä ratkaistu ilmeisen onnistuneesti eilen.
* Muuten rauhallista.

**Lumme**
* Finnan Haravoinnissa oli ongelmia, jotka johtuivat kahdesta tietueesta, joiden tiedot löytyi sekä biblio että deletedbiblio-taulusta. Tietojen poisto biblio-taulusta auttoi ja haravointi Finnaan onnistui taas.
* Virhe 500 ilmenee edelleen, esimerkkejä yritetään kerätä lisää.
* Muuten normaalia ylläpitoa.

**Helle**
* Myöhässä ja maksuja -toiminnossa näkyy mm. asiakkaan nimi. Palaverissa sovittiin, että nimeä ei piiloteta vaan piilotetaan koko toiminto. Tiketti https://github.com/KohaSuomi/Koha/issues/743
* Vanhentuneet varaukset -hakutuloksessa ollut Tuntematon asiakas -nimi on aiheuttanut ihmettelyä. Asiakastieto on käytössä anonymisoiduille ja poistetuille asiakastiedoille. Lisätty asiakastiedon huomautukseen lisätietoa käyttötarkoituksesta.
* Finto AI ( https://ai.finto.fi/?locale=fi ) lisätty Kohan yläreunan omiin linkkeihin

**Lappi**
* Normaalia päivystystä
* Viroon menemättömät viestit johtuvat sms-viestipalvelun rajoituksesta Suomen, Ruotsin ja Norjan puhelinnumeroihin. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-35-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 34 muistio

Aika: 22.8.2023 klo 9.15 <br />
Läsnä: Anneli Österman, Emmi Takkinen ja Lari Strand (Koha-Suomi), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Päivi Knuutinen ja Auli Rantasalo (Vaara), Tuomas Kunttu (Kyyti), Hanna Ikonen (Lumme), Reetta Pihlaja (Siilinjärvi), Pia Kusmin ja Leena Kinnunen (Lappi), Anni Rajala (Vaski)

**Yhteiset asiat**

* [Tiketti #336](https://github.com/KohaSuomi/Koha/issues/336) - brainstorming
  * kirjattiin tikettiin stormauksen tulos
* [Tiketti #725](https://github.com/KohaSuomi/Koha/issues/725) keskusteluun
  * kirjattiin tikettiin muutos tekstiin.
* [Finna-kehitysehdotus #4](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/4) - voidaanko viedä kehitysehdotus eteenpäin Finna-toimistolle, tuleeko mieleen jotain lisättävää?
  * Vaski voi lähettää ehdotuksen eteenpäin.
* [Viikon 34 päivitys](https://github.com/KohaSuomi/Koha/discussions/729)
* Nextit saadaan käytännössä työn alle vasta seuraavan huoltokatkon jälkeen, koska edustapalvelimelle pitää ensin tehdä asetusmuutos, joka vaatii konttien uudelleenkäynnistyksen -> käyttökatkos. Liittyy tikettiin #728
  * Uusi [Koha-23x-repositorio](https://github.com/KohaSuomi/Koha-23x) on jo luotu ja sinne kerätään taas uudempaan version liittyvää materiaalia.
* message_queue-taulua on siivottu OUTIssa, Vaskissa ja Vaarassa, koska varsinkin Vaskissa ja OUTIssa on ollut ongelmia viestien ison määrän kanssa. Aktiivisessa taulussa on 12 kk ja tällä hetkellä loput vuositauluissa. Tarkoituksena on yhdistää vuositaulut yhdeksi arkistotauluksi, kunhan saadaan tehtyä uusi skripti sitä varten. Arkistotaulun nimeksi tulee message_queue_archive.
  * Liittyy tiketteihin [Vaskin ilmoitusvälilehtiongelma tiketti 691](https://github.com/KohaSuomi/Koha/issues/691) ja [OUTIn ongelmat tiketissä 711](https://github.com/KohaSuomi/Koha/issues/711)

Etelästä pohjoiseen

**OUTI**
* Luetteloinnista tullut palautetta, että paikalliskantojen ja TäTin kuvailupohjat pitäisi päivittää uusimman MARC21-päivityksen mukaisiksi.
  * Formaattia on päivitetty viimeksi 15.6.2023.
  * OUTIsta puuttuu kolme viimeisintä päivitystä. Edellinen onnistunut päivitys on kesäkuulta 2021.
  * Tiketissä https://github.com/KohaSuomi/Koha/issues/256 on ilmoitettu, että pohjat päivittyisivät kerran kuukaudessa 1.1.2023 alkaen. Ilmeisesti automaattinen päivitys ei toimi?
* Asiakaspalvelusta tuli ihmettelyä, kun asiakas oli saanut kolmelle lyhytlainalle laina-ajaksi vain kuluvan päivän, jolloin lainat oli lainattu. Yhdelle neljän viikon lainalle oli tullut normaali laina-aika.
  * Lainausaika oli ajalla, jolloin OUTIssa oli ollut Koha-jumi, joten lainat oli lainattu Kohan offlinella.
  * Lokien mukaan lainat oli uusittu saman minuutin sisällä, kun ensilainaus oli tapahtunut eli kun lainat oli siirretty Kohaan.
  * Testasimme lainojen vientiä useamman kerran Kohaan, jolloin Koha tulkitsi uudelleen viennit lainojen uusinnoiksi.
  * Koska lyhytlainat eivät ole uusittavia, Koha antoi eräpäiväksi vain kuluvan päivän.
  * Olemme ohjeistaneet henkilökuntaa, että kirjastoissa jos useampi käyttää offline-lainausta yhtä aikaa, vain yksi siirtää kaikki lainat Kohaan.

**Vaara**
* Palautusautomaatti Joensuun pääkirjastossa temppuilee taas. Nyt ei saa yhteyttä admin-koneeseen eli näytölle ei tule palautukset näkyviin. Kahdesta palautuspisteestä vain toinen toimii tällä hetkellä.
* Erään asiakkaan maksujen kohdalla havaittiin ongelma, joka on alkanut jo versionvaihdosta. CalculateFinesOnReturn oli laitettu nextillä testausta varten päälle ja oli sitten unohtunut siihen asentoon, kun asetukset tuotiin tuotantoon.
 * Tässä tapauksessa asiakas oli maksanut yöllä 18.8. Finnan kautta myöhästymismaksujaan ja kesken maksun oli ajautunut myös cron-ajo maksujen päivittämiseksi. Asiakkas palautti kirjat saman päivän aikana. Asiakas oli uusinut lainansa 10.8., jolloin siihen mennessä kertyneet maksut olivat päivittyneet hänelle ja 18.8. tuli maksuvaiheessa myös palautettaessa päivittyvä maksu. 
 * Asiakkaan maksutapahtumien välilehdellä oli epäselvästi maksuja, joista osa oli hyvitetty (ilmeisesti automaattiseseti, kun asiakkaan tietoja tarkistettiin 18.8., koska virkailija ei ollut tehnyt mitään maksuille).
 * Tämä siis varoituksena ja muistutuksena: ei saa olla päällä CalculateFinesOnReturn-asetus yhtä aikaa maksujen päivittämiscronin kanssa.

**Kyyti**
* Kyytissä nousevat myöhästymismaksut 1.9.2023, joten laina- ja maksusääntöjä pääsee taas käymään läpi.
* Pari uutta nidetyyppiä perustettu, koska otamme käyttöön esineiden varaamisen siten, että noutokirjastoksi voi valita vain kotikirjaston.
* Uuden varmenteen jakaminen henkilökunnalle on aloitettu.

**Lumme**
* Perusylläpitoa.
* Käyty raporttikirjastoa aktiivisesti läpi.
* Jatkettu ns. tuplaverkkomaksujen selvittelyä Paytrailin kanssa. Löydetty paljon outouksia, esim. maksetut maksut eivät täsmää Kohan kanssa. Selvittely jatkuu.

**Siilinjärvi**
* Varmenteen jakelu ja asennukset aloitettu toistaiseksi ilman ongelmia
* Verkkomaksaminen käyttöön 1.9. alkaen, testaus meni ilman ongelmia

**Lappi**
* Jos asiakastiedoissa on virhetilanne, esim. pakollinen takaajatieto puuttuu, Finna antaa virheilmoituksen Järjestelmä pois käytöstä. Finna ei osaa avata virheellistä asiakastietoa, mutta ilmoitus on kuiten aika harhaanjohtava. Pia tekee asiasta tiketin ja on yhteydessä Finna-tukeen asian korjaamiseksi.
* Virolaiseen puhelinnumeroon ei ole mennyt viestit perille. Selvitetään. Vika ei ole Kohassa. Ja muihin ulkomaisiin numeroihin on mennyt viesit oikein.
* Osakohteiden piilotus tietuenäytöltä. Pohdittu tiketin #615 vaihtoehtoja.

**Vaski**
* Vaskin varmenne vanheni tänä aamuna, vaihto sujunut hyvin ja yhteydenottoja Vaskitukeen on tullut vain pari.
* Vajaa 4000 tietuetta ei ole indeksoitunut eikä löydy siten Kohan haulla [tiketti #727](https://github.com/KohaSuomi/Koha/issues/727). Emmi kokeilee auttaako uudelleenindeksointi.
* Hyllyvarausten käsittelyä mietitään Vaskissa ja Turku Data City on ehdottanut erillistä sovellusta, joka tuottaisi kirjastoille kohdennetut hyllyvarauslistat. Toisaalta Kohassa on vastaavana Varausjono-toiminnallisuus, jossa on tosin aiemmissa testauksissa kimpat havainneet ongelmia. Vaski ottaa asian esille asiantuntijaryhmässä, mietittävä miten olisi järkevää edetä ja edistettäisiinkö asiaa yhteisesti Koha-Suomessa.
* Viestipohjia päivitelty, muutettu noutomuistutus hyödyntämään asiakkaan kielivalintaa koska viestipohja ei tällä hetkellä käytä suomi/ruotsi/englanti-viestipohjia vaan pelkkää oletuspohjaa. Vaski lisäilee tekemänsä viestipohjat Koha-Suomen ohjeisiin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-34-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 32 muistio

Aika: 8.8.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Pirkko-Liisa Lauhikari (OUTI), Anni Rajala (Vaski), Tuomas Kunttu (Kyyti), Pia Kusmin (Lappi), Hanna Ikonen (Lumme)

**Yhteiset asiat**

* [Kausijulkaisujen vastaanottopäivän piilottaminen perustiedot-näytöltä](https://github.com/KohaSuomi/Koha/issues/544#)?
* Tällä viikolla ei ole päivitystä eikä huoltokatkoa
* Pääkäyttäjien ja Koha-Suomen vuoden 2022 -muistiot siirretty
* KohaCon viikolla 33, joten ei pidetä palaveria.

**Vaara**
* Vaarassa tapahtuu toisinaan tilanteita, jossa Koha vaatii uudelleenkirjautumista. Muut tilanteet ovat tapahtuneet yleensä lainaustilanteessa, esim. jokaisen lainatun kirjan jälkeen jollakin asiakkaalla. Mulla oli tilanne, jossa piti muokata asiakkaan tietoja ja yhtäkkiä Koha vaati kirjautumista. Tästä ei ole saatu vielä kuvakaappausta, joten tarkka sanamuoto ei ole muistissa. Tehdään asiasta tiketti, kunhan saadaan kuvakaappaus.

**OUTI**
* OUTIa on viime aikoina vaivanneet Koha-jumit aamusta n. klo 9.35-9.38. Jumeja on tullut lähes viikoittain, 1-2 krt/viikko. Ongelmaa on tutkittu ja epäilyksenä on, voisiko jumit aiheutua aamullisten viestien lähetyksistä, joita on OUTIssa paljon. Viestien lähetykset on jaettu nyt 1000 viestin eriin, josko auttaisi ongelmaan.
* Finna-tuesta on tullut vastauspostia asiakkaan Finna-tilin s-postiosoitteen päivittymisestä, josta olemme laittaneet useamman palautteen Finna-tukeen. Eli tällä hetkellä, jos Kohassa muutetaan tai poistetaan asiakkaan s-postiosoite tai jos asiakas itse tekee sen Finnassa, tieto ei päivity Finnaan asiakkaan Omat tiedot -sivun alareunassa olevaan Finna-tilin asetukset sähköpostikenttään. Tämän kentän s-postiosoitetta käytetään mm. verkkomaksukuitin lähetykseen ja unohtuneen salasanan palauttamiseen. Ilmeisesti korjaus olisi helppo toteuttaa, mutta sitä ei ole ainakaan vielä tehty.
* Yhdelle asiakkaalle tulee aina virheilmoitus ”System error 98”, kun hänen maksuja yrittää lähettää Kohasta Ceeposiin. Muilla asiakkailla ei ole vastaavaa ongelmaa. Kohan päästä ongelmalle ei ole löydetty syytä. Asiaa kysytty myös CPU:lta, näkisivätkö Ceeposin lokilta, mikä ongelman voisi aiheuttaa. (https://github.com/KohaSuomi/Koha/issues/715)

**Vaski**
* Uusi pääkäyttäjä Iina Niemi aloittanut.
* Kuitti- ja ilmoituspohjia ryhdytty siistimään ja hyödyntämään niissä enemmän Template toolkitiä.

**Kyyti**
* Kyytissä huomattu, että nidevaraus ei estäny uusimista. Selvisi, että Kyse on tiketin [#630](https://github.com/KohaSuomi/Koha/issues/630) ongelmasta.

**Lappi**
* Perusylläpitoa. Rauhallista ollut.

**Lumme**
* Perusylläpitoa.
* Virhe 500 esiintyy edelleen perustoimintojen yhteydessä. Asiaa selvitellään.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-32-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 31 muistio

Aika: 1.8.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Auli Rantasalo (Vaara), Pia Kusmin (Lappi), Hanna Ikonen (Lumme), Tuomas Kunttu (Kyyti), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Mikko Liimatainen (Vaski), Anneli Österman, Lasse Pouru ja Lari Strand (Koha-Suomi)

**Yhteiset asiat**

* Siirretyt ja päivitetyt dokumentaatiot:
  * [Finto-liitännäiset](https://koha-suomi.fi/dokumentaatio/finto/)
  * [Kuitti- ja viestipohjat](https://koha-suomi.fi/dokumentaatio/kuititjaviestit/)
  * [Miten tehdä SQL-raportteja](https://koha-suomi.fi/dokumentaatio/sqlkoulu/) ohje/koulutus/opas
  * [Termistö suomi-englanti](https://github.com/KohaSuomi/Koha-translations/wiki/Termist%C3%B6-suomi%E2%80%90englanti)
  * [PowerBI-raportit ja DAX-lausekkeet](https://koha-suomi.fi/dokumentaatio/powerbi/)
  * [Koha-Suomen hallituksen tiedotteet vuosilta 2021-2022](https://koha-suomi.fi/muistiot#koha-suomen-hallituksen-tiedotteet)
  * [Laskutusliitännäinen](https://github.com/KohaSuomi/koha-plugin-overdue-tool/wiki)
* [Viikon 31 päivitys](https://github.com/KohaSuomi/Koha/discussions/706)
* Asiakasvarmenteet jaettu ma Matrixin kautta pääkäyttäjille.
* Jos teillä on SQL-kyselyitä, jotka käyttävät koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements-taulua, korjatkaa ne käyttämään biblionumberia biblioitemnumberin sijaan. Jos käytetään biblioitemnumberia, kyselyt voivat jäädä junnaamaan. Tauluun lisättiin kesäkuussa biblionumber-kenttä.

Etelästä pohjoiseen

**Vaara**
* ei mitään erityistä, normaalia ylläpitoa
* laskutuksen käyttäjäongelma johtui käyttäjäoikeuksien siivouksesta, joka tuli tehtyä liian tarkasti eli poistin liikaa oikeuksia

**Lappi**
* Saarenkylä avannut ovensa ja niteet palautettu saatavana-tilaan. Tiedonhakusivulle jäänyt niteille ei-lainattavissa merkintä, vaatii uudelleen indeksoinnin.
* Perusylläpitoa

**Lumme**
* Perusylläpitoa
* Finnassa tullut lisää asiakkaille ns. palautuksia maksetuista maksuista. Ongelmaa selvitellään Paytrailin ja Finnan kanssa.

**Kyyti**
* Vasta palattu lomalta, ei raportoitavaa

**OUTI**
* Ei mitään erityistä, normaalia tukitoimintaa ja ylläpitoa.

**Vaski**
* Kausijulkaisutilauksissa viimeinen numero ja sisäinen laskuri eivät näytä aina päivittyvän samassa rytmissä. Tämä aiheuttaa ongelman, jossa vuoden viimeiselle numerolle muodostuu numeroksi ensi vuoden viimeinen numero.
* Vaskin testille laitettu uudet triggerit mobile ja smsalertnumber synkronointiin. Korjaavat virheen null-arvoisten kenttien päivittymisessä. Tehty tiketti [708](https://github.com/KohaSuomi/Koha/issues/708) triggereiden päivittämisestä kaikille kimpoille.
* Kellutussääntöjä siivottu ja saatu vähennettyä noin kolmannes säännöistä. Huomattiin samalla, että floatrulesiin voi kommentoida Perlin # kommenteilla. Tehty tiketti [709](https://github.com/KohaSuomi/Koha/issues/709) floatrules ohjeiden päivittämisestä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-31-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 30 muistio

Aika: 25.7.2023 klo 9.15 <br />
Läsnä: Pia Kusmin (Lappi), Auli Rantasalo (Vaara), Anneli Österman ja Lasse Pouru (Koha-Suomi), Johanna Miettunen (3AMK), Hanna Ikonen (Lumme), Piia Semenoff (OUTI), Mikko Liimatainen (Vaski)

**Yhteiset asiat**

* Dokumentaatioita siirretty Redminestä Koha-Suomen verkkosivuille ja TäTiin sekä vanhoja päivitetty
  * [IntranetUserCSS](https://koha-suomi.fi/dokumentaatio/intranetusercss/) päivitetty versioon 22.11
  * [IntranetUserJS](https://koha-suomi.fi/dokumentaatio/intranetuserjs/) päivitetty versioon 22.11
  * [Käyttöönotto-ohjeita](https://koha-suomi.fi/dokumentaatio/kayttoonotto-ohjeita/)-sivu, jossa ohjeistus Asteriin, Editx:ään, laskutustyökaluun, RDA ja poikkeava pääsana sekä Fintoon
  * [Ohjeita ongelmatilanteisiin](https://koha-suomi.fi/dokumentaatio/ongelmatilanteet/)
  * TäTin toimintaohjeet siirretty Redminestä TäTin sisäiseksi sivuksi. Linkki samassa paikassa TäTin yläpalkissa kuin ennenkin.
* TäTin IntranetUserCSS:iä sekä BorrowerUnwantedFields-järjestelmäasetusta säädetty. Myös turhia asiakasmääreitä poistettu. Varaustunnusta en vielä saanut poistettua, koska se on käytössä käyttäjätunnuksilla.

Pohjoisesta etelään

**Lappi**
* Ei mitään mainittavaa.

**OUTI**
* Viime viikolla asiakas maksoi verkkokirjastossa kirjastomaksunsa 21.6. klo 00:00, jonka jälkeen hän uusi lainansa klo 00:01-00:02. Klo 00:03 hänelle muodostui uudet myöhästymismaksut siten, että maksut kertyivät vanhojen, juuri maksettujen maksujen päälle. Todennäköisesti asiakas meni maksamaan maksujaan juuri silloin, kun maksuajo on käynnistymässä/käynnissä. https://github.com/KohaSuomi/Koha/issues/694

**Vaara**
* Kaksi työntekijää on kertonut, että lainaustilanteessa kortin ja kirjan nidetarran lukemisen jälkeen, ohjelma on heittänyt kohan kirjautumistilaan. Uudelleen kirjauduttua Kohaan ohjelma palautuu asiakkaan lainaukseen ja kirja on mennyt lainaan. Toisen työntekijän kohdalla tämä oli tapahtunut seitsemän kertaa eli seitsemän lainan kohdalla. Jos tätä vielä tapahtuu, otetaan kuvakaappaus ja tehdään tiketti.
* Työntekijä ihmetteli miten toisinaan kun peruuttaa varauksen samalla kun palauttaa varauksen, tulee noutamattoman varauksen maksu. Anneli tiesi kertoa, että tämä johtuu siitä mitä kautta peruuttaa varauksen.

**Lumme**
* Perus ylläpitoa.
* Tuli vastaan tapaus, jossa virkailija oli palauttanut lokien mukaan asiakkaan kirjan, mutta kirja oli jostain syystä pysynyt asiakkaalla lainassa. Toinen palautus poisti kirjan asiakkaan lainoista.

**Vaski**
* Kellutussääntöjä pyritään yksinkertaistamaan, koska suuren sääntömäärän hallinnointi käy hankalaksi, kun kelluttavien kuntien määrä kasvaa.
* Viestiasetuksien ja matkapuhelinnumeroiden siivouksia käynnissä. Paljon pois pudonneita mobile ja smsalertnumber numeroita palautettu backup-taulusta.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-30-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 29 muistio

Aika: 17.7.2023 klo 9.15 <br />
Läsnä: Anni Rajala (Vaski), Veli-Pekka Marjoniemi (OUTI), Leena Kinnunen (Lappi), Reetta Pihlaja (Siilinjärvi), Kati Sillgren (Helle), Auli Rantasalo (Vaara), Anneli Österman ja Lasse Pouru (Koha-Suomi)

**Yhteiset asiat:**

* Elasticsearchin indeksit -listaus lisätty Kohan ohje suomeksi -> Tiedonhaku -> [Hakukone Elasticsearch ja sen indeksit](https://koha-suomi.fi/dokumentaatio/tiedonhaku/#108-hakukone-elasticsearch-ja-sen-indeksit)
* Valmiit SQL-raportit lisätty [Raporttikirjastoon](https://koha-suomi.fi/dokumentaatio/raporttikirjasto/) Ohjeet-sivulle.
* Uudet asiakasvarmenteet jakoon vasta vkolla 31. Jakelutavan sopiminen. Laitetaan Matrixiin uusi varmenne ja salasana.
  * Vaski: Askolle, Annille ja Mikolle Matrixissa
  * Lappi: Pialle ja Marialle
  * OUTI: Piialle, Pirkko-Liisalle ja Vellulle
  * Siilinjärvi: Reetta (paikalla 14.8. alkaen)
  * Vaara: Päivi, Auli, Irina
  * Lumme: Hanna, Katja
  * Kyyti: ?
  * Helle: Kati
  * Kirkes: Erika
* Kohan ohje suomeksi - viimeiset viilailut
  * numerointien tarkistukset, onko kaikilla otsikkotasoilla numerointi?
  * noudattaako kuvat nykyohjeistusta?
  * vertaile vielä yhteisön manuaaliin, löytyisikö jotain uutta lisättävää.

Etelästä pohjoiseen

**Vaski**
* Kohassa katko ma 17.7., johtui samasata messages_queue -taulun lukittumisesta kuin viime keskiviikonkin katko Vaskissa.
* Noutomuistutuksen lähetyksestä poistettu email-pakotus, jotta saatiin lähetys noudattamaan asiakkaan viestiasetuksia. Ennen muutosta noutomuistutus lähti kaikille asiakkaille, joilla oli sähköposti, asia tuli ilmi kun tästä tuli asiakaspalautetta.

**OUTI**
* Koha Offline -työpöytäsovellus aiheuttanut henkilökunnassa hämmennystä, kun samassa kirjastossa eri asiakaspalvelupisteissä sovellusta käyttäville on tullut näkyviin toistenkin virkailijoiden offline-lainat. Testauksessa huomattu, että kun lataa tiedoston Kohaan, niin saman kirjaston offline-lainat näkyvät kaikille. Ne voivat näkyä "Odottavat yhteydettömän tilan toimet" -linkin takana tai siinä vaiheessa, kun lähettää yhteydettömän tilan lainaustiedoston eli klikkaa "Lähetä yhteydettömän tilan lainaustiedosto (*.koc)" -linkkiä ja etenee koko matkan ”Näytä käsittelyä odottavat yhteydettömän tilan tapahtumat”-linkkiin asti ja klikkaa sitä. Todettu siis ominaisuudeksi, joka hoituu ohjeen päivittämisellä ja siitä tiedottamisella.
* Muuten rauhallista, normaalia tukitoimintaa.

**Lappi**
* Korjattu luettelopohjien osakenttien järjestystä ja poistettu First received date -kentät
* Yhtä lukuunottamatta Lapin Redminen tiketit käyty läpi, siirretty Githubiin tai suljettu. 
* Edelleen rästiin jääneiden tehtävien hoitoa
* Vuoronvaihto: Pia ja Maria palaa lomalta, Leena jää lomalle

**Siilinjärvi**
* Jäänyt tekemättä kirjastokortin numeron ja käyttäjätunnuksen yhtenäistäminen, tehty tukipyyntö [#692](https://github.com/KohaSuomi/Koha/issues/692) elokuulle
* Verkkomaksamisen käyttöönotto nytkähtänyt vähän eteenpäin, tavoiteaikatauluna elokuun loppu
* Koha-ohjeen päivitys kesken 12.1 Asiakaslistojen osalta, koska tiketti [#638](https://github.com/KohaSuomi/Koha/issues/638) odottaa korjausta
* Reetta jää lomalle, Marko palaa lomalta

**Vaara**
* Noutamattomien varauksien listalla oli asiakastunnisteena " AnonnymousPatron", joka johtuu lainahistorian tyhjentämisestä. Siitä olikin jo tiketti tehty.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-29-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 28 muistio

Aika: 11.7.2023 klo 9.15 <br />
Läsnä: Leena Kinnunen (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Kati Sillgren (Helle), Hanna Ikonen (Lumme), Piia Semenoff (OUTI), Anneli Österman (Koha-Suomi), Reetta Pihlaja (Siilinjärvi)

**Yhteiset asiat:**

* biblioitems.datereceived, joka oli KS-muutos ja tiputettiin versionvaihdossa pois, on edelleen kiinni kuvailupohjissa kentässä 942$1
  * liitos pitäisi ottaa pois (ja mahdollisesti korvata toisella sarakkeella) - se onnistuu Poista napilla 942-kentän tietoja katsottaessa. Pääkäyttäjät poistavat liitoksen manuaalisesti kuvailupohjista.
  * ![kuva](https://github.com/KohaSuomi/kohasuomi.github.io/assets/33121325/1f529cb9-80a1-4721-8e95-5aa10d57563b)
  * korvaavaa ei keksitty äkkiseltään. Mietitään ajan kanssa, onko tarvetta.

* [Virkailijoille tullut versionvaihdossa liikaa oikeuksia maksuissa #572](https://github.com/KohaSuomi/Koha/issues/572)
  * nämä voisi tarkistaa joka kimpasta ja kommentoida tikettiin onko näille tarve tehdä jotakin, tehdään korjaukset sitten kaikille kerralla

* Finnan ongelmien ja kehitysehdotusten läpikäynti (jossain ennalta sovitussa aamupalaverissa).
  * Sovitaan aika lomien jälkeen, kun on enemmän väkeä paikalla.

* [KohaConin-ohjelma](https://perlkohacon.fi/Schedule.html#) (näyttää päivittyvän jatkuvasti)

Pohjoisesta etelään

**Lappi**
* Kohan ohje päivitetty Lapin vastuualueelta
* Osassa tietueita on 100-kentän 9-osakentässä RLIN-numero (Koha-Auth-Number), esim. biblionumber=1743001 tekijätieto muodossa an:128065, ei au.
Ilmeisesti RLIN-numero on syntynyt jossain vaiheessa, jos on ollut päällä automaattinen auktorisointi, 
ja se on luonut joka kerta tekijätietoa tallennettaessa uuden yksilöllisen tunnisteen. 
Tästä seuraa, että hakutuloksen tekijätieto ei löydä muita tietueita ko. tekijältä. Tehty tiketti #682. : Korjaantui vaihtamalla järjestelmäasetuksen UseAuthoritiesForTracings valinnaksi: Älä käytä auktoriteettitietueiden numeroita tekstitiedon sijasta asiasanahauissa.
* Hoidettu rästiin jääneitä pikkukorjauksia Kohaan
* Tukipyyntöjen osalta rauhallista

**OUTI**
* Rauhallista, perustukihommia
* Koha Offline-lainauksessa tuli vastaan kummallisuus, että virkailijoiden omiin henkilökohtaisiin tallennuspaikkoihin tallentamat Kohan Offline-lainat näkyivät toisilla koneilla eri käyttäjien Koha-istunnoissa, kun lainoja siirrettiin tiedostoista Kohaan. Vika ei todennäköisesti ole Kohassa vaan tutkitaan ensin onko kyseessä Oulun sisäinen tiedosto-ongelma. 

**Vaara**
* Viime viikolla raportoimani ongelma PowerBI-raporttien proxy errorista johtui muuttuneesta käytännöstä. Lari sai sen korjattua ja Emmi teki [tiedotteen](https://github.com/KohaSuomi/Koha/discussions/685)
* Vastaanotettavien kuljetusten listalla näkyy varattujen niteiden kohdalla asiakkaan nimi ja hänen sähköpostiosoitteensa. Tein siitä tiketin [687](https://github.com/orgs/KohaSuomi/projects/4/views/1?pane=issue&itemId=32700366) 
* Muuten rauhallista, aikaa siivota tietokantaa 

**Lumme**
* Ei raportoitavaa, pienimuotoisten ongelmien selvittelyä.
  
**Helle**
* Asiakastiedon vasemman tietoruudun Tili on lukittu -teksti aiheuttanut henkilökunnassa hämmennystä. Palaverissa saatu tieto, että tekstiin ei tule muutosta/tarkennusta.
* Palaverissa mainittu kuvailupohjan biblioitems.datereceived liitoksen poisto: Helleen jätetään toistaiseksi. 942|1-kentän mahdollisista arvoista on apua tikettiin #392 (Tänään 34182 tikettiin liittyvällä niteellä on ko. kentän arvona muu päiväysarvo kuin 2018-09-04.)

**Siilinjärvi**
* Ei mainittavaa.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-28-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 27 muistio
Aika: 4.7.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen (Vaara), Leena Kinnunen (Lappi), Veli-Pekka Marjoniemi (OUTI), Mikko Liimatainen (Vaski), Reetta Pihlaja (Siilinjärvi)

**Yhteiset asiat:**

Etelästä pohjoiseen

**Vaara**
* Muutama PowerBI-raportti päätyy proxy erroriin, muut raportit toimivat. Nämä nyt "vialliset" ovat toimineet kesäkuun alussa.
* Löytynyt toukokuun lopussa lisätty asiakastietue, josta puuttuu osoitetiedot, jotka ovat pakollisia tietoja. Hämmentävää.
* Lähetetty Kansalliskirjastoon sähköpostia PerlKohaConin ohjelmasta, jota ei vieläkään näy missään.

**Lappi**
* Lapin deleted-taulujen aikaleimat korjattu. Löytynyt erikoisia niteitä, joilta puuttuu kuvailutietue #606
* Joillakin tietueilla 100-kentässä 9-attribuuttissa (Koha-Auth-Number) yksilöllinen numerosarja. Aiheuttaa sen, että hakutuloksessa tekijätiedon linkki ei löydy muita tuloksia. Tehty tiketti #682.
* Kemiin tullut uusi omatoimiautomaatti.

**OUTI**
* Ei mitään erityistä.

**Vaski**
* Mynämäen kellutus alkanut eilen. Ongelmia ei ilmennyt. Kellutus kiinnostaa nyt muissakin kunnissa.
* Verkkomaksuissa havaittu pitkiäkin viiveitä. Maksujen poistumisessa Kohasta voi kestää. Maksukuittauksetkaan eivät ole menneet asiakkaille perille. Paytrailin päässä ei havaittu ongelmia. Jatketaan selvittelyä Kansalliskirjaston kanssa.

**Siilinjärvi**
* Kohassa ei erityistä, muut kesätyöt pitävät kiireisenä

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-27-muistio) - [Palaa sivun alkuun](/paakayttajat2023)
  
## Viikko 26 muistio
Aika: 27.6.2023 klo 9.15 <br />
Läsnä: Leena Kinnunen (Lappi), Päivi Knuutinen (Vaara), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Kodo, Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi), Mikko Liimatainen (Vaski)

**Yhteiset asiat:**
* https://github.com/KohaSuomi/Koha/issues/606
  Kodo on oikaissut epäsynkan kaikilta muilta kimpoilta paitsi Lapilta. Lapin korjaus tehdään 4.7.

Pohjoisesta etelään

**Lappi**
* Tiketti 623 vielä korjaamatta
* Rauhallista, ei kummempia tapahtumia

**Vaara**
* Enon kirjaston remonttisulku tehty maanantaiaamuna
* Tiketti https://github.com/KohaSuomi/Koha/issues/252 Kielikoodien fasetissa olevasta ongelmasta putkimerkkien kanssa. Lasse on tehnyt raportin, jolla saa haettua näitä koodeja sisältäviä nimekkeitä, mutta koska fasetin pitäisi toimia myös tuon sinänsä formaatin mukaisen koodin kanssa, tehdään siitä tiketti Bugzillaan.

**OUTI**
* Koha on antanut Oulussa pari kertaa Ceeposissa maksetun maksun jälkeen ilmoituksen ”Something went wrong, check the logs!” Yhteistä maksuille on ollut se, että molemmista maksuista puuttuu maksuriveiltä/osalta maksuriveistä maksun id-numero. Ei liity versiopäivitykseen, koska toinen maksutapahtumista oli tullut jo ennen versiopäivitystä. Tiketti: https://github.com/KohaSuomi/Koha/issues/665
* Oulun hankinnasta tuli palautetta, että taas olisi alkanut tulla tuplatietueita tilausvaiheessa. Esimerkkitapauksessa tilaukset olivat eri kirjastoille. Tietueista ei löytynyt mitään eroa. Tarkistin molemmat tilaukset ja tämä oli ainut, josta löysin tuplatietueen. Tiketti: https://github.com/KohaSuomi/Koha/issues/666

**Helle**
* Kohaan kirjautumisen sisällön määrityksissä oli käytössä script-tagi. Kehittäjä Emmi Takkiselta uudet määrittelyt kirjautumiseen ilman script-tagia.

**Siilinjärvi**
* Ei mainittavaa

**Vaski**
* Varausten kuljetustiloja peruutettaessa nidekuljetustilat eivät poistu. Tämä olisi tarpeen joissain tilanteissa, koska nyt kuljetustilan saa sellaiseen tilaan, ettei sitä saa helposti purettua niteeltä.
* Bugzillasta löytynyt joitain tikettejä koskien havaittuja ongelmia. Tiketöidään myös GitHubiin.
  
[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-26-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 25 muistio
Aika: 20.6.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Irina Halminen (Vaara), Leena Kinnunen (Lappi), Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Lari, Mikko Liimatainen (Vaski)

**Yhteiset asiat:**
* Emottomien osakohteiden poisto, tiketti [#348](https://github.com/KohaSuomi/Koha/issues/348) tehty jo tammikuussa. Olisi tärkeää saada siivottua näitä emottomia osakohteita pois tietokannoista/Päivi
* TäTin nalkuttimen päivittäminen - mikä tilanne?
* Kirjastokortin saaminen näkymään tietueen varaukset-sivulle. Asiasta tehty tiketti [#664](https://github.com/KohaSuomi/Koha/issues/664)

Etelästä pohjoiseen

**Vaara**
* ei mitään isompaa ylläpidettävää
* Reijolaan tulee uusi automaatti

**Lappi**
* Tiketti 623: Tornion niteillä näkyy hakutuloksessa edelleen 31.5. poistettu not_loan-tila Tornion varastoidut. Nidetiedoissa tila näkyy oikein.
* Käyttäjätunnusten puolivuositarkistus käynnissä
* Leena päivystää seuraavat 4 viikkoa
* Rauhallista ollut.

**OUTI**
* Normaaleja tukitöitä, ei mitään erityistä.
* Kohan ohje suomeksi päivittelyä.

**Vaski**
* Noutomuistutuksen käyttöönotossa yllätys, kun asetus olikin asiakkailla valmiiksi valittuna ja viestejä lähti liikkeelle ennen kuin oli tarkoitus.
* Tietovarastoprojektin osalta toivottu kimppojen välistä yhteistyötä, jotta rajapintatoteutuksessa voitaisiin ottaa huomioon muut vastaavat tarpeet.
* Kohaconin aikataulua odotellaan, jotta tiedettäisiin, minä päivinä olisi hyvä osallistua.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-25-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 24 muistio
Aika: 13.6.2023 klo 9.15 <br />
Läsnä: Leena Kinnunen (Lappi), Päivi Knuutinen (Vaara), Hanna Ikonen (Lumme), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Anni Rajala (Vaski)

**Yhteiset asiat:**
* Kirjataan muistiin: automaattien toimittajat Lyngsoe, Bibliotheca ja Mikroväylä ovat ilmoittaneet, että automaateissa voi ottaa käyttöön myös pidempiä PIN-koodeja kuin nyt on vain neljä numeroa.
  * Selvitetään onko pitempää PIN-koodia mahdollista käyttää kaikissa palveluissa, joihin niillä kirjaudutaan.
  * Vaski on lupautunut testaamaan.
* Varausjono-raportti / Koha-Suomen hyllyvarausraportti -> uudelleentarkasteltavaksi kumman ylläpitäminen olisi järkevintä?
Keskusteltu tiketissä [#578](https://github.com/KohaSuomi/Koha/issues/578). Kannattaisiko pääkäyttäjäryhmä asian selvittelyä, voidaanko edentää ehdotus uudelleentarkastelusta asiantuntijaryhmään? (Anni / Vaski)
  * Vaski ottaa asian uudestaan esille pääkäyttäjäpalaveriin kesälomien jälkeen. Keskustellaan silloin laajemmalla osanottajamäärällä miten näiden varaus-raporttien osalta edetään.

Pohjoisesta etelään

**Lappi**
* Tietue aiheuttaa Kohaan 500-virheen, syynä puutteellinen 942-kenttä. Vastaavia tietueita on vajaa 10, kehittäjä korjaa. 
* Kuvailun hakukenttä tyhjene, jos hakulauseella ei löydy mitään. Toimii siis toisin kuin tiedonhakukenttä. Olisiko joku järjestelmäasetus vai ominaisuus?
* Käyttäjätunnuksia tehty tiheään kesätyöntekijöille. 
* Muuten rauhallista. 

**Vaara**
* Lauantaina oli tapahtunut pari ihmeteltävää asiaa, joista tein nyt tiketit:
* https://github.com/KohaSuomi/Koha/issues/645 Varaustunnus vaihtui anonymisoiduksi vanhentuneiden varausten listalla, kun asiakas oli poistanut lainahistoriansa
* https://github.com/KohaSuomi/Koha/issues/646 Varauksen noutoaika pidentyi viikolla, kun tulostettiin uusi odottavan varauksen kuitti. Asiakkaalle ei lähtenyt viestiä uudesta noutoajasta
* Edge-selain kysyy varmenteen kahteen kertaan, toinen kerta Vaaran testikannalle. Ilmeisesti vika Meitan asetuksissa, teen sinne palvelupyynnön korjata asia.
* Muuten normaalia ylläpitoa.

**Lumme**
* Virhe 500 toistuu säännöllisen epäsäännöllisesti palautuksissa. Asiaa selvitellään edelleen. 
* Automaateilla otettiin käyttöön mahdollisuus, että asiakas saa lainattua niillä hyllyvarauksen, jota ei ole vielä palautettu Kohassa tai automaatilla.
* Muuten normaalia ylläpitoa.

**OUTI**
* Finvoice-laskujen ääkkösongelma saatu oletettavasti kuntoon.
  * Viime viikon laskutusajoissa oli muita ongelmia (Raahen laskutusaineistoa ei saatu ajettua ja Oulun laskutusaineisto oli ilmeisesti Monetralla siirretty väärälle laskutuspohjalle), joten korjauksen onnistuminen varmistuu tällä viikolla.
* Pieni erä Raahen Finvoice-laskuja saatu lähtemään, mutta laskut eivät ainakaan eilen vielä näkyneet Raahen Monetralla.
  * Palaverin jälkeen saimme tiedon, että laskut ovat siirtyneet nyt myös Monetralle.
* Väärälle asiakkaalle mennyt s-postia, kun Finna-tilin sähköpostikenttä ei päivity, jos sähköpostiosoite muutetaan Kohassa. Laitettu taas palautetta Finna-tukeen.
* Asiakkaalta tullut palautetta, että verkkokirjastossa kun asiakas siirtyy Lainat-sivulta Varaukset-sivulle, sivusto pyytää kirjautumaan uudelleen.
  * Ongelma saatiin toistettua, kun odotettiin Finnan kirjautumisajan umpeutumiseen asti. Ei ole saatu vastausta asiakkaalta, että johtuuko virhetilanne timeoutista.
* Takaajatieto vielä linkitettynä, vaikka asiakas on jo täysi-ikäinen. Tiketti: #641
  * Tiketissä mainittu raportti 167 Takajalalliset asiakkaat voi olla nopea ja helppo korjata toimivaksi. Sen avulla voisimme tarkistaa onko meillä enemmänkin takaajallisia henkilöasiakkaita?
* Kohan ohje suomeksi -ohjetta päivitetty.

**Vaski**
* Yksi työntekijä havainnut tapauksen, jossa asiakastietojen tallentaminen onnistui ilman osoitetietoja. Työntekijä muisteli, että kentät olisivat lomakkeelta puuttuneet kokonaan, mutta ei ollut asiasta täysin varma. Joka tapauksessa osoitetiedot olivat tyhjät, kun asiakasta tallentamisen jälkeen tarkasteli. Raporttihaulla (address = '') löytyi toinen vastaava tapaus, asiakastietue tallennettu 2.6.2023. Ei keksitty selitystä, mutta raportoidaan tämä vielä tiketiksi.
* Palautetta tullut siitä, ettei Koha-Suomen sivuilla haku löydä ohjeita. Todettiin, että haku on Githubin, joka ei ole erityisen hyvä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-24-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 23 muistio
Aika: 6.6.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Kati Sillgren (Helle), Piia Semenoff ja Pirkko-Liisa Lauhikari (OUTI), Reetta Pihlaja (Siilinjärvi), Tuomas Kunttu (Kyyti), Hanna Ikonen (Lumme), Anni Rajala (Vaski), Leena Kinnunen (Lappi)

Etelästä pohjoiseen

**Vaara**
* normaalia ylläpitoa 
* ihmettelimme jälleen eilen sitä, että lainojen ja varausten määrä ei noudata laina- ja maksusäännöissä tehtyjä asetuksia. Teen tiketin, jotta kehittäjät voisivat jossain vaiheessa tutkia, eikö tälle todellakaan voi mitään. Ongelma on ollut olemassa jo vuosia.

**Lappi**
* Normaalia ylläpitoa
* Asiakkaan syntymäaika oli osunut kesäaikaan siirtymisen päivämäärälle, jonka vuoksi asiakkaan viivakoodi antoi virheen 500. Korjattu vaihtamalla syntymäpäivä. Emmi hoitaa selvitystä eteenpäin, tiketti #620
* Saarenkylän kirjasto remontissa 22.6. - 30.7. Saarenkylän kirjaston aineistolle ajetaan not_loan-tila. Muuten ei aiheuta suuria muutoksia, sillä kiinnioloajan kirjastoauto leikkii olevansa Saarenkylän kirjasto ko. kirjaston pihalla

**Helle**
* Asiakastiedon muokkauksen Käyttökieli-asiakasmääre on nyt Asiakas identiteetti -osiossa.
* Asiakastiedon muokkauksen Muut määreet -osio piilotettu.

**OUTI**
* OUTIn Finvoice-laskuissa puuttuvat ääkköset laskutettavan teoksen nimestä ja tekijältä. Tiedot ovat ”ArticleName”-kentässä. Asiakkaan Ilmoitukset-sivulla näkyvässä laskussa ääkköset näkyvät oikein, mutta kun laskutiedot siirtyvät kuntien laskutusohjelmiin, josta laskut lopullisesti tulostetaan, ääkköset ovat hävinneet ko. kentän tiedoilta. Ongelmaan ehkä löydetty ratkaisu. Piia tehnyt uudet testilaskut tänään, joista pääsemme tarkistamaan asian. Tiketti: https://github.com/KohaSuomi/Koha/issues/621
* OUTIssa deleted-tauluissa biblioitemnumberin ja biblionumberin epäsynkkaa. Ei onnistu tietueen tai/ja niteen poistot, tulee virhe 500. Ongelmasta tiketeissä: https://github.com/KohaSuomi/Koha/issues/604 ja https://github.com/KohaSuomi/Koha/issues/606.
* Asiakkaalta Matkapuhelin-kentästä ja SMS-kentästä ovat puhelin numerot kadonneet. Ruksi noutoilmoituksen lähettämisestä testiviestinä on asiakkaalla päällä.  Ei näy, että hänen tietojaan olisi kukaan muokannut. OUTIssa on tullut muutama tapaus esille ja Kyytissä yksi. Ongelmasta tiketissä: https://github.com/KohaSuomi/Koha/issues/607.
* Sähköpostina lähetettävien ilmoitusten lähettäjäosoite muuttunut versopäivityksessä. Nyt lähettäjänä on taas noutokirjaston sähköpostiosoite, kun se pitäisi olla noreply@koha-suomi.fi. Tiketti: https://github.com/KohaSuomi/Koha/issues/616
* Asiakas oli ilmoittanut, että hän oli saanut sähköpostiin ilmoituksen, että kirjastokorttisi PIN-koodi vaihdettiin. Asiakas oli kertonut, ettei hän ole sitä tehnyt. Asiakkaan muutoslokilla ei näkynyt tietoa, että PIN-koodi olisi vaihdettu asiakkaan tai virkailijan toimesta. Asiakkaan Ilmoitukset-sivulla ei ollut myöskään ko. ilmoitusta. Asiakkaan huollettavalle, jolla sama s-postiosoite kuin huoltajalla, ei ole PIN-koodia vaihdettu. Tietokannasta ei löydy muita asiakkaita, joilla olisi sama s-postiosoite kuin tällä henkilöllä. Asiakkaalta pyydetty s-posti vielä nähtäväksi, jotta voimme varmistaa, onko posti lähetetty OUTIsta vai mahdollisesti jostain toisesta Koha-Suomen kimpan kirjastosta, jossa olisi asiakkaan kaima ja gmaili olisi jättänyt huomiotta osoitteessa olleen mahdollisen pisteen. *Kokouksen ulkopuolinen tieto: Asiakkaalta saatu kopio s-postiviestistä. Viesti oli tullut OUTIsta." Tehty tiketti: https://github.com/KohaSuomi/Koha/issues/629*

**Siilinjärvi**
* Ei mainittavaa Kohassa
* Siilin kuvailija kävi opintomatkalla Vaarassa, kiitos opastuksesta!

**Kyyti**
* Uuden asiakkaan tervetuloviesti laitettu päälle eilen.
* Tuomas jää lomalle tämän viikon jälkeen ja palaa elokuussa. Kotkan Roosa Väisänen paikalla suuren osan kesää.

**Lumme**
* Normaalia ylläpitoa.
* Lumme-Finna temppuili viime viikon loppupuolella, ongelma saatiin korjattua kehittäjien puolella. Tarkkaa syytä sivujen ulkonäköasetusten katoamiselle ei saatu.
* Lumpeissa oli käytössä asetus, jolla lainoja sai uusittua, vaikka niihin oli varaus, jos vapaana oli saatavana olevia niteitä. Asetus jouduttiin ottamaan pois käytöstä, sillä se tuotti ongelmia lehtien varauksissa. Myös mahdolliset asiakkaiden kokemat ongelmat omien Finna-tietojen näkemisessä saattoivat johtua tästä asetuksesta. Tilannetta seuraillaan.

**Vaski**
* Finnassa otettu käyttöön kuljetustilaisen varauksen peruminen.
* Kohassa otettu käyttöön asetus AllowRenewalIfOtherItemsAvailable, joka sallii varatun teoksen lainan uusimisen silloin kun teoksella on varaukset täyttäviä niteitä vähintään niin paljon kuin varauksia. Lumpeissa asetuksesta oli luovuttu, koska asetus ei osannut huomioida nidevarauksia ja näin näyttää olevan edelleen (oli unohtunut Vaskilta testata). Yhteisöstä löytyi tiketti aiheesta ja sen pohjalta Githubissa nyt [tiketti 630](https://github.com/KohaSuomi/Koha/issues/630) jossa toiveena saada yhteisön korjaus käyttöön.
* Hitautta havaittu asiakashaussa, lisäksi raporteilla tullut proxy erroria ja Finnassa epäonnistunut lehtitietueiden saatavuustietojen haku. Asiakashaun hitautta havaittu muuallakin (muttei kaikkialla). Vaski tekee havainnoistaan tiketin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-23-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 22 muistio

Aika: 30.5.2023 klo 9.15 <br />
Läsnä: Anneli Österman ja Lari Strand (Koha-Suomi), Kati Sillgren (Helle), Päivi Knuutinen ja Irina Halminen (Vaara), Leena Kinnunen ja Pia Kusmin (Lappi), Reetta Pihlaja (Siilinjärvi), Susanna Sandell (Vaski), Piia Semenoff, Pirkko-Liisa Lauhikari, Veli-Pekka Marjoniemi (OUTI), Hanna Ikonen (Lumme)

**Yhteiset**
* Vaskin asiakasvarmenne vanhenee jo elokuussa
  * jotta päästään kaikissa kimpoissa samaan uusimistahtiin, uusi varmenne tulee kaikille jakoon ma 24.7.2023.
  * muilla kimpoilla uusi tulee siis jo aiemmin käyttöön ja vanha on käytettävissä pidempään kuin Vaskissa.
  * Pääkäyttäjät: vaihto mielummin jo toukokuussa, koska kesä-elokuu loma-aikaa kaikkialla
* [Kaksivaiheisen kirjautumisen käyttöönotto](https://koha-community.org/manual/22.11/en/html/patrons.html#two-factor-authentication-in-the-staff-interface)
* Show analytics/Näytä osakohteet -linkin piilotus?
  * Päätös: Piilotetaan linkki ja otsikko css:llä. Anneli tekee.
* [Viikon 22 päivitys](https://github.com/KohaSuomi/Koha/discussions/598)

Pohjoisesta etelään

**Vaara**
* Ceepos-kassan toiminnallisuutta kaivataan takaisin Joensuun pääkirjastossa eli maksujen kuittausta automaattisesti.
* asiakkaan varausten näkymisen ja Finnan kautta varausten teon ongelma johti siihen, että havaittiin alle 40 nidettä, joissa 952w-kenttä oli väärä eli 0000-00-00. Syynä tähän todennäköisimmin käyttäjän virhe eli kopioitu 952d-kentästä päiväys, joka on eri muodossa kuin kentässä w ja johtaa tallennuksessa päiväyksen nollautumiseen. Vaikka asiasta on tiedotettu, kaikki eivät muista, että päiväys tallentuu automaattisesti kun nidetieto tallennetaan. Tämän vuoksi piilotettiin w-kenttä näkyvistä eri kuvailupohjissa. Virheelliset päiväykset korjattu käsin.
* Enon kirjasto menee muutaman viikon sulkuun kesällä remonttien (ulkoa ja sisältä), sen aiheuttamista muutoksista tehty tiketti.

**Lappi**
* Asiakashaku aiheuttaa sekaannusta, kun hakukentissä on erilaiset hakukriteerit oletuksena. #556
* Tulevat ja loppuvat remonttit työllistävät taas kesänaikana.
* Intranetuserjs:ssä oli väärä attribuuttiarvo sotusiilon rimpsussa, Anneli korjasi. Sotut/avaimet vielä korjaamatta. 
* Normaalia ylläpitoa ja samoja pikkukorjauksia, kun muillakin kimpoilla.

**Siilinjärvi**
* Kohassa ei suurempaa mainittavaa, muutoin verkkomaksun käyttöönotto ja henkilökuntatilanne ajankohtaisia
* Testataan tiketin #476 css:t

**Vaski**
* Broomworksin Puppe saapumisvalvontatyökalua ollaan hankkimassa.
* Selvityksen alla otetaanko Hypernovan Koha SaaS-palveluna Oppimateriaalikeskukselle. Hypernova tarjoaa Kohan yhteisöversiota.
* Vaskissa Pääkäyttäjän vakityö tarjolla.
* Finnassa oli vanhoilla Apple-laitteilla ongelma, jonka Ere ilmeisesti sai ratkaistua.

**OUTI**
* Asiakkaille on tullut vielä miinusmerkkisiä maksuja, koska he pystyvät maksamaan verkkomaksupalvelussa saman maksun kahteen kertaan. Maalis-toukokuussa tuplamaksuja viidellä asiakkaalla.  

**Lumme**
* Asiakashaku aiheuttaa Lumpeissakin pientä sekaannusta. 
* Lumpeissa oli myös väärä attribuuttiarvo sotusiilon rimpsussa, Anneli korjasi.
* Normaalia pikkukorjauksia niin kuin muuallakin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-22-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 21 muistio

Aika: 23.5.2023 klo 9.15 <br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi), Pia Kusmin (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Kati Sillgren (Helle), Piia Semenoff, Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Reetta Pihlaja (Siilinjärvi), Tuomas Kunttu (Kyyti), Anni Rajala (Vaski), Hanna Ikonen ja Katja Valjakka (Lumme)

**Yhteiset**
* Miten menee versionvaihdon jälkeen?
  * Opittavaa versionvaihdon prosesseista yms?
    * kalenteri suljetuksi jo ma, koska asiakkaat valittivat, että olisi ollut vielä pari tuntia aikaa uusia lainoja.
    * omien toimintojen arviointi, onko kaikelle edelleen tarvetta?
    * Finna kertoi vain, että "väärä käyttäjätunnus tai salasana", mikä oli hämmentänyt asiakkaita. Yleensä kertonut, että taustajärjestelmään ei saa yhteyttä.
    * tuotannossa tuli esille virheitä, joita ei ollut testeissä ilmaantunut tai huomattu -> kiinniolo jatkossa puoltoista päivää?
    * redusoituun kantaan isompi setti tietueita, asiakkaita, lehtitilauksia. Osakohteita enemmän. Enemmän erilaisissa nidetiloissa olevia niteitä. Asiakastiedot: asiakkailta puuttui huollettavia ja varauksia -> helpompi, jos asiakkaan kaikki huollettavat, varaukset ja lainat otettaisiin mukaan.
* Kaksvaiheinen kirjautuminen käyttöön superlibrarian-tunnuksille, jos käytössä on työälyluuri.
  *  TwoFactorAuthentication -järjestelmäasetukseen _Salli_
* Palataan takaisin normaaliin tikettien seurantaan ja päivitystahtiin.
  * Uudet tiketit Koha-repositorioon. (Muistakaa tehdä tiketit, ei töitä sähköpostin tai Matrixin kautta, ohi tiketöinnin)
  * Päivitykset kerran viikossa tiistaisin.
  * Muistakaa sulkea tekemänne tiketit, kun ne ovat valmiit/ratkaisu ehdotettu.
* [Tiketti 117](https://github.com/KohaSuomi/Koha-22x/issues/117) - hakutuloslistan piilotus aiheuttanut palautetta. Haku toimii vain kirjastokortilla tai asiakkaan koko nimellä (kaikki etunimet ja sukunimi). Piilotus tehty, jotta ei voi hakea esille kaikkia tietokannan asiakastietoja ja vältetään turhia asiakastietojen katselua.
  * Päätös: Viedään asia asiantuntijaryhmän päätettäväksi seuraavalla ehdotuksella: Poistetaan hakutulostaulukon piilotus ja piilotetaan taulukosta syntymäaika, osoite ja puhelinnumero -sarakkeet.
  * Sarakeasetukset eivät toimi, [tiketti 571](https://github.com/KohaSuomi/Koha/issues/571) 
* [Kohan ohje suomeksi -wikin päivityksen seurantatiketti](https://github.com/KohaSuomi/Koha/issues/549)
  * Sovittu, että kuvaa ei tarvitse vaihtaa, jos sisältää tiedot olennaisilta osin. Vaihdettava kuitenkin, jos kuva ei vastaa nykyistä ohjeistusta.
  * Jos kuvan vaihtaa, pääsee helpoimmalla, kun nimeää uuden kuvan samalla nimellä kuin entinen oli ja vie sen sitten githubiin. Vanha korvataan uudella.
* kehitysehdotukset [#555](https://github.com/KohaSuomi/Koha/issues/555) ja [#556](https://github.com/KohaSuomi/Koha/issues/556)
* [Vanhentuneet noutamattomat varaukset](https://tiketti.koha-suomi.fi/projects/koha-suomen-dokumentaatio/wiki/Valmiita_SQL-raportteja#Vanhentuneet-noutamattomat-varaukset) -raportti päivitetty käyttämään HOLDID-asiakasmäärettä.
* Laitetaanko total issues -cronit pois päältä? Aiheuttaa nyt [ylimääräisiä valutuksia](https://github.com/KohaSuomi/Koha-22x/issues/190). [Redmine tiketti 1849](https://tiketti.koha-suomi.fi/issues/1849) liittyy myös aiheeseen.
  * kokeillaan outissa, auttaisiko toistaiseksi pelkkä 942$0-kentän kytkennän katkaiseminen biblioitems-tauluun?
* [Tiistain päivityksen tiedote](https://github.com/KohaSuomi/Koha/discussions/566)
* [Tiketti 560](https://github.com/KohaSuomi/Koha/issues/560) - MARC-virheraporttien linkit Raporttien etusivulle
* Lomien päivitys [yhteystiedot-wikiin](https://github.com/KohaSuomi/Koha/wiki/Koha-yhteystiedot)

**Vaara**
* Vaarassa kaivataan takaisin nappulaa kuljetuksen peruuttamiseen palautustilanteessa. Koitetaan säätää kohdilleen.

**Kyyti**
* Kotkassa ja Iitissä ollut ongelmia kellutuksessa: niteitä menee tarpeettomasti kuljetustilaan. Kotka selvittää asiaa.

**Vaski**
* Päivityksen jälkeen tullut odotettua vähemmän viestejä henkilökunnalta, eniten ongelmia on aiheuttanut saapumiskäsittelyn epäonnistuminen josta tehtynä tiketti [#562](https://github.com/KohaSuomi/Koha/issues/562)

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-21-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 20 muistio

Aika: 16.5.2023 klo 9.15 <br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi)

* Käytiin läpi, mitä pitää tehdä tuotannossa ennen kuin kirjastot voidaan avata sekä erilaisia versionvaihdon ongelmia.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-20-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 19 muistio

Aika: 9.5.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen ja Irina Halminen (Vaara), Leena Kinnunen (Lappi), Tuomas Kunttu (Kyyti), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (Outi), Reetta Pihlaja (Siilinjärvi), Anneli Österman ja Lari Strand (Koha-Suomi), Kati Sillgren (Helle), Hanna Ikonen ja Katja Valjakka (Lumme)

**Yhteiset**
* Viikon 20 eli 16.5. eli versionvaihtopäivän pääkäyttäjäpalsu pidetään klo 10.15.
  * tarkistetaan yhdessä, että tarpeelliset muutokset ja toimet on tehty tai tulee tehdyksi.
* Testejä tai testaustuloksia kaivataan vielä ainakin näihin:
  * [SIP muutos - ksdev/ks-0043-KD-2608 #15](https://github.com/KohaSuomi/Koha-22x/issues/15)
  * [koha-plugin-add-marc-field-001 (KPM001) #85](https://github.com/KohaSuomi/Koha-22x/issues/85)
  * [koha-plugin-delete-biblio-components (KPDELC) #94](https://github.com/KohaSuomi/Koha-22x/issues/94)
* Keskiviikkona 10.5.2023 testi-kantojen päivitys versioon 22.11.
  * harjoitellaan varsinaista ensi viikon päivitystä.
  * testi-kannat pois käytöstä päivityksen ajan.

Etelästä pohjoiseen.

**Vaara**
* Kuvailun käyttöohjetta päivitetty uuteen versioon, vielä on osittain kesken. Viimeistely sitten versionvaihdon jälkeen.
* Toveri-plugin toimii Hypernovan mukaan uudessa versiossa, toivottavasti myös käytännössä versionvaihdon jälkeen.
* Virheilmoitus EDItX-tilaussanomissa, joka johtuu Elasticsearch-virheestä. Näiden käsittelyyn pitäisi saada parempi käytäntö, jottei jälkikäteen korjattavia tuplatilauksia syntyisi.

**Lappi**
* Tullut jonkinverran EditX-virheitä: virheellinen sanoma tai puuttunut title. Korjattu/korjaantuneet. 
* Nextiä testattu ja lisätty Githubin mukaan toimintoja ja säätöjä

**Kyyti**
* Virkailijoiden kirjastokorttinumero- ja käyttäjätunnuskenttiä on yhdenmukaistettu
* Samalla perustettu uusia asiakastyyppi, johon menevät vinkkaus- ym. työkortit. Sen myötä laina- ja maksusääntöjä päivitetty.

**OUTI**
* OUTIssa testattu verkkomaksuja Finna-nextillä niin, että siellä oli tuotantopalvelimen asetukset. Maksuprosessissa ei ilmennyt ongelmia. 
* Testattu Emmin kanssa Ceepos-maksuja nextin kanssa. Maksujen lähetys nextiltä Ceeposiin toimii, mutta maksetun maksun kuittaus takaisin Ceeposista Kohaan ei vielä toimi.
* OUTIn verkkomaksupalvelu ei toiminut ma 8.5. n. klo 11-15. CPU oli päivittänyt Oulun kaupungin verkkomaksusivustolle uuden sertifikaatin, mutta sertifikaattiin liittyvä yksi tiedosto oli valittu väärin, joka aiheutti ongelman.

**Siilinjärvi**
* Meiltä oli jäänyt testaamatta meille tärkeä Tulosta ilmoituksia #93 eli testataan seuraavaksi vielä se.

**Lumme**
* Nextin testailua ja lisätty GitHubin mukaan toimintoja.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-19-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 18 muistio

Aika: 2.5.2023 klo 9.15 <br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi), Susanna Sandell (Vaski), Päivi Knuutinen ja Auli Rantasalo (Vaara), Katja Valjakka ja Hanna Ikonen (Lumme), Reetta Pihlaja (Siilinjärvi), Piia Semenoff ja Veli-Pekka Marjoniemi (OUTI), Kati Sillgren (Helle)

**Yhteiset**
* [Z39.50-haku tiputtaa 001-kentästä BTJ:n kontrollinumeron pois](https://github.com/KohaSuomi/Koha-22x/issues/171)
  * Mitä tämän kanssa tehtäisiin?
  * Yksi vaihtoehto voisi olla ottaa asetus pois päältä ja tuoda nykyversion 001-liitännäinen uuteenkin versioon.
  * **Päätös**: Tuodaan vanha 001-liitännäinen, eikä käytetä autocontrolnumber-järjestelmäasetusta.
* Jos teette tuotantoon viestipohjiin muutoksia, muistakaa tehdä ne myös nextille.

Pohjoisesta etelään.

**OUTI**
* Raahen Finvoice-laskutus nytkähti taas eteenpäin (on ollut työn alla viime syksystä asti ja etenee hitaasti). Sovittu, että Raahe alkaa laskuttamaan tuotannossa vasta versionvaihdon jälkeen. Koetamme saada sen siiheksi osaltamme niin valmiiksi kuin mahdollista.
* Normaalia ylläpitoa ja versionvaihtoon liittyviä töitä

**Vaski**
* 19.4. Koha-katko pääsi Turun Sanomiin raflaavilla otsikoilla
* Tätistä valunut virheellisesti tietoja muutaman osakohteen päälle. Syy toistaiseksi tuntematon. Vaski tekee tiketin.

**Vaara**
* ei mitään eristyistä, mutta mainitsen uuden nidetyypin testauksen tuloksia
* Vaarassa tarvitaan uusi nidetyyppi, jonka laina-aika on 7 vrk, rajoitus 1, on varattavissa mutta ei uusittavissa, lyhyt noutoaika varauksella.
Nide ei saa kellua eikä sitä kuljeteta, eli se on lainattava aina kotikirjastostaan.
 * Testasin Vaaran tuotannossa lainaamista ja varaamista. Laina- ja maksusäännöissä nidetyypille laitoin varauksia sallituksi 1 kaikkiin kolmeen varausta koskevaan asetukseen, hyllyvaraus sallittu "Jos yhtään ei ole saatavilla". Nidetyypeittäin oleviin varaussääntöihin laitoin varaussääntö-sarakkeeseen "Mistä tahansa kirjastosta" ja varauksen noutokirjasto täsmää "niteen kotikirjasto".
 * Testaukseni mukaan varauksen rajoittaminen ei onnistu, vaikka säännössä määritellään vain yksi varaus sallituksi. Asiakas voi Finnan kautta
varata useita saman nidetyypin nimekkeitä. Kuljetuksen estäminen sen sijaan onnistuu, eli niteen voi varata noudettavaksi vain niteen kotikirjastosta. Jos asiakkaan kotikirjasto on joku muu eikä vaihda noutopaikkaa, tulee virheilmoitus "The supplied pickup location is not valid" (en ole vielä keksinyt, miten tuon saa suomeksi, mutta eiköhän se jostain onnistu). Hyllyvaraus sen sijaan ei onnistu, varauspainike ei tule ollenkaan näkyviin Finnassa, jos nide on saatavana-tilassa.
 * Nextillä uuden nidetyypin testaaminen ei oikein onnistunut, sillä varaaminen ei onnistu. Varausnapissa lukee Tarkista varaus. Kun siitä klikkaa, saa tekstin: "Kirjastojärjestelmään ei saatu yhteyttä. Tietoja, jotka liittyvät tiliisi kirjastossa, ei voida näyttää. Jos ongelma jatkuu, ota yhteyttä kirjastoon."

**Lumme**
* Lumpeiden chat-palvelu loppui 2.5. vähäisen käytön takia.
* Lumpeilla lisättiin myös maksujen osamaksumahdollisuus Finnaan.

**Siilinjärvi**
* Keskusteltu Kodon kanssa asiakasrekisterin siivoamisesta.
* Ei muuta mainittavaa.

 [Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-18-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 17 muistio

Aika: 25.4.2023 klo 9.15 <br />
Läsnä: Tuomas Kunttu (Kyyti), Veli-Pekka Marjoniemi, Piia Semenoff, Pirkko-Liisa Lauhikari (OUTI), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Pia Kusmin (Lappi), Reetta Pihlaja (Siilinjärvi), Hanna Ikonen, Katja Valjakka (Lumme), Susanna Sandell (Vaski)

**Yhteiset**
* [Nexteiltä siirrettävät](https://github.com/KohaSuomi/Koha-22x/wiki/Versiovaihdon-muistiinpanot#nextilt%C3%A4-tuotantoon), siirretäänkö asiakasrajoitukset ja asiakasmääreet?
  * Siirretään asiakasmääreet. Huolehdittava, että Nextillä on oikea määrä määreitä ennen versionvaihtoa.
  * Ei siirretä asiakasrajoituksia. Mikään kimppa ei ole vielä ainakaan lisännyt sinne uusia rajotteita.
* miten testailut menee?

Etelästä pohjoiseen

**Kyyti**
* Mitä kaksivaiheinen tunnistautuminen vaatii puhelimeen?
TOTP:tä tukeva ohjelma, Kohan ohjeiden mukaan esim. Google Authenticator, andOTP, FreeOTP
* Nextillä Kaikki lainat -kuitissa oleva uusintakertojen määrä <<items.renewals>> ei enää toimi, mutta <<issues.renewals_count>> vaikuttaisi toimivan.
* Nextillä varausten järjestys ei toimi oikein, koska uusi varaus menee ensimmäiseksi jonossa. Liittyy kuulemma tietokantojen redusointiin, esim. Vaskissa toimii oikein.
* Miten voisi saada esim. esineen varattavaksi siten, että sen voisi noutaa vain niteen sijaintikirjastosta (ettei lähde kuljetukseen)?
Voisi testata laina- ja maksusääntöjen Oletusvaraussääntö nidetyypeittäin -kohtaa. Varauksen noutokirjasto täsmää: niteen sijaintikirjasto.

**OUTI**
* Tuotanto-Finnassa asiakastietojen muutospyynnöt lakkasivat toimimasta ja asiakkaat saivat virheilmoituksen "Pyyntöä ei voitu käsitellä. Yritä uudestaan."  Ongelma oli myös Vaskissa. Ongelma johtui siitä, että Vaskissa ja OUTIssa oli ylikirjoitettu sivupohja myresearch/change-address-settings.phtml. Kun ylikirjoitus poistettiin, muutospyynnöt lähtivät taas toimimaan. Koska samaa ongelmaa on myös osalla next-Finnassa, niin kokeiltiin samaa korjausta myös siellä. Korjauksella saatiin varaustunnuksen muutospyyntö toimimaan, mutta osoitetietojen muutospyynnöt antavat edelleen next-Finnassa virheilmoituksen. 
* Link Mobility (SMS-palvelu) ottaa uuden varmenteen käyttöön 25.4.2023 klo 15.00. OUTIssa ei aiheuta toimenpiteitä Kohan eikä Webkaken osalta. 
* Oulussa on mennyt ja menee kirjastoja (Puolivälinkangas, Kaukovainio, Asema) kiinni remontin tai muun syyn vuoksi. Kiinnimenot ovat aiheuttaneet muutoksia Kohaan. 
* OUTIssa testataan next-Finnassa verkkomaksuja Ceeposin verkkomaksuportaalin kanssa. 

**Vaara**
* Viime viikolla otettiin käyttöön Finnaan muutos, jossa asiakas voi valita mitkä maksut maksaa eli ei ole pakko maksaa kaikkia maksuja kerralla.
* Vaaran henkilökunta on testannut nextiä ja useampi on kommentoinut, että hakutulokseen pitäisi saada niteen luokkatieto näkyviin.
* Testattu testattavia tikettejä ja muutakin mieleen juolahtavaa.

**Lappi**
* Muutamia EditX-virheitä tullut
* Normaalia ylläpitoa ja versionvaihtoon liittyviä töitä

**Siilinjärvi**
* Kaksivaiheinen tunnistautuminen ei ehkä tule käyttöön ainakaan heti
* Ei muuta mainittavaa

**Lumme**
* Lumpeissa sama ongelma kuin Outissa next-Finnassa, mitä tulee asiakkaiden osoitteenmuutospyyntöihin.
* Lumme-next Lumpeiden Koha-ryhmän kokeiltavaksi.
* Kokeiltiin auktorisoitujen arvojen muutoksia, jotta Tilanahtaus-status saataisiin toimimaan järkevästi Kohassa ja Finnassa. Kokeilut tämän osalta jatkuvat. 

**Vaski**
* Versiovaihdon asiakastiedotus alkamassa ja Nextin testaus laajennetaan koko henkilökunnalle
* Oppimateriaalikeskuksen järjestelmän uusiminen suunnitteilla

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-17-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 16 muistio

Aika: 18.4.2023 klo 9.15 <br />
Läsnä: Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi), Päivi Knuutinen ja Irina Halminen (Vaara), Hanna Ikonen (Lumme), Mikko Liimatainen (Vaski), Tuomas Kunttu (Kyyti)

**Yhteiset**

* Asiakasviestien ajastukset tällä hetkellä / Kodo
  * Helle 8.00 overdue_notices.pl, 8.40 advance_notices.pl, 9.10 membership_expiry, kirjeet ei lähde
  * Kyyti 8.40 advance_notices.pl, 9.00 overdue_notices.pl, 9.10 membership_expiry.pl, kirjeet 14.30 ja 20.50
  * Lappi 8.40 advance_notices.pl, 9.00 overdue_notices.pl, 9.10 membership_expiry.pl, kirjeet 20.50
  * Lumme 6.00 holds_reminder.pl, 9.10 membership_expiry.pl, 12.25 advance_notices.pl, 12.29 overdue_notices.pl, kirjeet 20.50
  * Outi 8.40 advance_notices.pl, 9.00 overdue_notices.pl, 9.10 membership_expiry.pl, kirjeet 20.50
  * Siili 0.20 overdue_notices.pl, 0.25 advance_notices.pl, kirjeet ei lähde
  * Vaara 00.25 advance_notices.pl, 22.04 overdue_notices.pl, 22.00 membership_expiry.pl, kirjeet 13.30 ja 22.15
  * Vaski 9.00 overdue_notices.pl, 12.19 advance_notices.pl, 9.10 membership_expiry.pl, kirjeet 20.50
  * Osa ajastuksista vaikuttaa omituisilta, osa päällekkäin huoltojen kanssa, runsaasti kimppakohtaista varianssia, miksi näin ja löytyisikö yhteistä linjaa näihin?
  
  **Päätös:** Ajastetaan viikkopalaverin 11 päätöksen mukaisesti: Kaikille kimpoille aina (ei vain huoltoikkunan aikaan) viestien generointi klo 9.11 ja viestien lähetys alkamaan klo 9.30. Uudet ajastukset unohtuivat tehdä 12.4., joten laitetaan päälle mahdollisimman pian eli jo tänään 18.4.2023. 
 
 * Hellen, Kyytin ja Lumpeen jonossa roikkuvat 'pending' tilaiset kirjeet aiheuttavat meille valvonnan virheilmoituksia / Kodo
   * Message queue has messages pending for 108 days (Kyyti)
   * Message queue has messages pending for 214 days (Helle)
   * Message queue has messages pending for 3 days (Lumme)
   * Voidaanko merkitä senteiksi tai failedeiksi esimerkiksi cronilla?
   
   **Päätös:** Helle, Kyyti ja Lumme tarkistavat itse säännöllisesti (mielellään päivittäin) pendign-tilassa roikkuvat viestit ja hoitavat ne itse pois. Jos viestejä paljon, voi tarvittaessa tehdä tiketin, niin kehittäjät poistavat ne ajona.

* Käykää läpi kirjepohjat ja muistakaa, että kirjeviestirajapinta / suomi.fi / postitus- ja kuorituspalvelut _eivät_ rivitä tekstejä automaattisesti. Jos tekstirivit ovat liian pitkiä, niin rivit yksinkertaisesti katkeavat kirjeellä oikeasta laidasta paperin reunan tullessa vastaan. Ainakin Juvan kirjeissä näyttää olevan hyvin pitkiä rivejä. Muistakaa myös, että nimeke voi yksinäänkin olla jo satoja merkkejä pitkä: "Sopimus Belgian kuningaskunnan, Tanskan kuningaskunnan, Saksan liittotasavallan, Helleenien tasavallan, Espanjan kuningaskunnan, Ranskan tasavallan, Irlannin, Italian tasavallan, Luxemburgin suurherttuakunnan, Alankomaiden kuningaskunnan, Portugalin tasavallan, Ison-Britannian ja Pohjois-Irlannin yhdistyneen kuningaskunnan (Euroopan unionin jäsenvaltiot) ja Norjan kuningaskunnan, Itävallan tasavallan, Suomen tasavallan ja Ruotsin kuningaskunnan välillä Norjan kuningaskunnan, Itävallan tasavallan, Suomen tasavallan ja Ruotsin kuningaskunnan liittymisestä Euroopan unioniin." / Kodo

  **Päätös:** Hyvä tarkistaa kaikissa kimpoissa kirjeviestipohjien rivitykset.
  
* Tikettien tekeminen ja kommentointi -ohje siirretty Redminestä Githubiin [Koha-repositorion wikiin](https://github.com/KohaSuomi/Koha/wiki/Tikettien-tekeminen-ja-kommentointi).

* Käännösmuutos varauksenteko-sivulle?
  * Varauksenteko-sivulta on piilotettu asiakashaun hakutulostaulukko, mistä johtuen asiakkaan hakeminen onnistuu käytännössä vain kirjastokortilla tai koko nimellä niin, että tuloksena on yksi ainoa vastaus. Hakukentän yläpuolella on kuitenkin ohje "Syötä kirjastokortin numero tai osa nimestä:" eli englanniksi "Enter patron card number or partial name:". On ehdotettu, että käännöstä muutettaisiin.
  * Jos muutos tehdään, on se sellainen, mikä pitää ylläpitää Koha-Suomessa jokaisessa versionvaihdossa. Muita vastaavia muutoksia on esim. phone-kentän nimeäminen Lankapuhelimeksi ja mobile-kentä Matkapuhelimeksi (yhteissö primary phoe ja other phone). Koska muutostarve johtuu meidän omasta piilotuksesta (pyritään vähentämään asiakastietojen katseluja), ei ole perusteltua muuttaa yhteisön käännöstiedostoihin käännöstä.
  
  **Päätös:** Kannatettiin ajatusta, että ohjeteksti olisi sen mukainen, kuin haku tulee tehdä eli ohjeistetaan, että asiakashaku tulee tehdä kirjastokortilla tai asiakkaan koko niemllä. Kehittäjät ehdottivat, että käännöstiedostojen ajojen jälkeen ajettaisiin aina automaattisesti skripti, joka muuttaisi kaikki Koha-Suomen omat ylläpidettävät käännösmuutokset halutuiksi. Kysytään vielä Annelin mielipidettä. 

* [Damaged-tila yliajaa muut tilat Finnassa](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/2#issuecomment-1506892120)
  * Susanna: Finnassa pystytään priorisoimaan tilat. Priorisointi on toteutettuna tällä hetkellä meidän testinäkymään vaski.finna-pre.fi, mutta sitä on ilman Kohaan pääsyä muiden hankala testata. Meidän testauksen perusteella kaikki näyttää menevän oikein. Miten edetään?
  
  **Päätös:** Vaski testaa nextillä ja versionvaihdon jälkeen tuotannossa. Vaskin kokemusten perusteella katsotaan, tehdäänkö tilojen priorisointi Finnassa myös muille kimpoille.

**OUTI**
* OUTIn uuden version henkilökunnan testaukset alkoivat 17.4. Jokaista Kohan ja verkkokirjaston osa-aluetta testaa kaksi henkilöä ja kirjaavat testaushuomiot testaustaulukkoon. Isompia ongelmia ei ainakaan ensimmäisen päivän aikana tullut esille.
* Kansalliskirjastosta oli tullut ilmoitus, että joissakin Melindan tietueissa on käytössä 852 5-osakenttä, joka ei oikeasti kuulu formaattiin, joten Heikkisen Antti pyysi, että säädetään TäTin Nalkuttimeen asetukseen, että myös tämä kenttä pääsee läpi.

**Siilinjärvi**
* Ei mainittavaa

**Vaara**
* Tiina Vauhkonen lopettanut pääkäyttäjänä
* Vaaran henkilökunnalle annettu oikeus koekäyttää nextiä. Vielä ei ole juurikaan tullut kommentointia.

**Lumme**
* Automaatit toimivat taas.
* Nextin testaus laajenee Lumpeiden pääkäyttäjille.

**Vaski**
* Verkkomaksun testauksesta voi sopia Kansalliskirjaston kanssa, että Nexteille halutaan kiinni testausympäristö. Vaskissa oma toteutus testattavana.
* Damaged-tilojen priorisointia verkkokirjastossa testattu. Kuljetus ohittaa damaged-tilat. Not-loan on väärässä kohtaa.

**Kyyti**

* Nextillä ISSUESLIP-kuitissa oleva uusintakertojen määrä <<items.renewals>> ei enää toimi. Kokeilin vaihtaa siihen <<issues.renewals_count>> ja se ilmeisesti toimii. Kannattaa muidenkin testata.
* Nextillä perustiedot-näytöltä puuttuu Vie/Tuo-painike. Teen siitä tiketin.
* Sivulla https://github.com/KohaSuomi/Koha-22x/wiki/Versiovaihdon-muistiinpanot lukee, että tiputetaan seuraavat taulut: okm_statistics, okm_statistics_logs ja biblio_data_elements. Varmistin, että nämä siis todella poistuvat. Näitä korvaavat uudet taulut ovat: koha_plugin_fi_kohasuomi_okmstats_biblio_data_elements ja koha_plugin_fi_kohasuomi_okmstats_okm_statistics

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-16-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 15 muistio

Aika: 11.4.2023 klo 9.15 <br />
Läsnä: Anni Rajala (Vaski), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Hanna Ikonen (Lumme), Anneli Österman, Pasi Kallinen ja Kodo Korkalo (Koha-Suomi)

**Yhteiset**
* Oletuskieli -> suomi, tehdään ajo kaikille asiakkaille, jotta ei tulostu sekakielisiä kuitteja. [Liittyy tikettiin Koha-22x/#151](https://github.com/KohaSuomi/Koha-22x/issues/151).
* Muistattehan tehdä tiketit sip-tunnuspyynnöistä. Ei pelkkää sähköpostiviestiä, jotta muutoksista/pyynnöistä jää jälki tikettijärjestelmään ja ne saadaan tilastoitua.
* [Ehdota esitystä KohaConiin 14.-18.8.2023](https://github.com/KohaSuomi/Koha/discussions/492)

**Vaski**
* Turun pk:n musaosasto kiinni 4 viikkoa, ei-saatavilla olevalle aineistolle lisätty erikoistila.
* Finna-testaus nextiä vasten suurimmaksi osaksi tehty.
* Verkkomaksamisen testaus? Sovittiin, että Vaski selvittää Finna-toimistolta josko olisi mahdollista järjestää testausmahdollisuus. Testata pitäisi kolmessa eri ympäristössä (Turun oma toteutus, Ceepos, suora Paytrail-yhteys), mutta palataan testaaviin kimppoihin seuraavassa pääkäyttäjäpalaverissa.
* Testattu asetusta AllowRenewalIfOtherItemsAvailable nextillä (versiossa 22.x tullut muutoksia) ja testauksen perusteella tulkitsee nyt saatavilla oleviksi niteiksi ainoastaan hyllyssä olevat niteet (joilla ei ole erikoistilaa) sekä koti-/siirtoyksikköön kuljettavat niteet. Asetus voi mahdollisesti edelleen aiheuttaa suorituskykyongelmia, OUTIssa on taannoin jouduttu ottamaan asetus pois käytöstä koska asiakkaat eivät pääseet omiin tietoihinsa. Kyytissä asetus on nytkin käytössä. Vaski kokeilee mahdollisesti asetuksen käyttöönottoa heti versiopäivityksen jälkeen.

**OUTI**
* Ei mitään erikoista.

**Kyyti**
* Kyytin toinen pääkäyttäjä on Roosa Väisänen Kotkasta. 

**Lumme**
* Automaateilla palvelinongelmia. Ongelmia selvitellään.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-15-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 14 muistio

Aika: 4.4.2023 klo 9.15 <br />
Läsnä: Veli-Pekka Marjoniemi (OUTI), Kati Sillgren (Helle), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Reetta Pihlaja (Siilinjärvi), Hanna Ikonen ja Katja Valjakka (Lumme), Pia Kusmin (Lappi), Anneli Österman (Koha-Suomi)

**Yhteiset**
- Koha-Suomen harjoittelija Ville esittäytyi.
- Versionvaihdon työt aloitetaan ma 15.5.2023 klo 22 tietokanta-ajoilla. Eli palvelut on pois käytöstä tuosta lähtien.
- Uusia pääkäyttäjiä: Lumme ja Kyyti
- huoltoikkuna tulossa 12.4.2023, tiedossa katkoja tietokanta-ajojen vuoksi. [Huoltotiedote](https://github.com/KohaSuomi/Koha/discussions/491)

Pohjoisesta etelään.

**OUTI**
* Normaalia ylläpitoa ja nextin testausta.

**Vaara**
* Normaalia ylläpitoa ja nextin testausta.

**Siilinjärvi**
* Normaalia ylläpitoa ja nextin testausta.

**Lumme**
* Normaalia ylläpitoa ja nextin testausta.

**Lappi**
* Normaalia ylläpitoa ja nextin testausta.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-14-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 13 muistio

Aika: 28.3.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Heli Auranen, Timo Pesonen, Katja Valjakka (Lumme), Reetta Pihlaja (Siilinjärvi), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Pia Kusmin (Lappi), Anneli Österman ja Lari Strand (Koha-Suomi)

**Yhteiset**
* nideryhmien käyttöönottoaikataulu
  * Suurin osa pääkäyttäjistä oli sitä mieltä, että käyttöönotto vasta versionvaihdon jälkeen
* cardnumber-kenttään käyttäjätunnus, jotta voidaan ottaa käyttää triggeri, joka pitää cardnumberin ja userid:n synkassa keskenään.
* [Uudet virkailijaoikeudet](https://github.com/KohaSuomi/Koha-22x/wiki/Uudet-virkailijaoikeudet)
* SIP2-pyynnöt, teettehän myös tiketin, kun laitatte tunnuspyynnön sähköpostiin.
* [Kimppojen logot voi laittaa tähän tikettiin talteen](https://github.com/KohaSuomi/Koha-22x/issues/18)
* OPACAllowUserToChangeBranch - Finna ei noudata tätä, joten ei merkitystä, mitä valitaan. Voi laittaa Suspended varmuuden välttämiseksi, jos siihen joskus tulee muutosta.

Kuulumiset etelästä pohjoiseen.

**Vaski**
* Koha-testaus työn alla, pyritään testaamaan tietyt seikat pääsiäiseen mennessä.
* Pohdittiin, onko tarpeen vaihtaa Finnan oletusnäkymä versionvaihdon yhteydessä. Luultavasti ei, mutta testataan Omat tiedot -sivu ja varausten toiminta erityisen tarkasti. Testauksen perusteella päätetään, miten toimitaan. Vaihdossa toki täytyisi varmistaa tilastojen siirtyminen näkymästä toiseen, joten mieluummin pidettäisiin vanha oletusnäkymä.
* Oltiin kiinnostuneita siitä, mihin kellonaikaan päivitys alkaa 16.5., jotta voidaan tiedottaa henkilökunnalle ja asiakkaille. Ei vielä tarkkaa tietoa, Anneli sanoi että selvittää tätä.

**Vaara**
* ei mitään erityistä, nextin testausta ja tuotantotietokannan siivousta vajavaisten aineistotietojen (aineistotyyppi epämääräinen yläkäsite) takia

**OUTI**
* Ei mitää erityistä. 
* Yhdestä kirjastosta on tullut ihmettelyä, että yhdellä asiakkaalla mobiilikortin viivakoodi ei ollut näkynyt verkkokirjaston Kirjastokortit-sivulla, kun hänen maksuraja oli ylittynyt. Viivakoodin tilalla oli ollut  teksti "Asiakas lainauskiellossa" tjs. Kun maksut oli maksettu, mobiilikortti oli tullut näkyviin. Tuessa testattu, mutta vastaavaa ongelmaa ei ole saatu aikaan. Myös Finna-tilillä mobiilikortti näkyy, vaikka asiakkaan maksuraja on ylittynyt. Nyt jälkikäteen tuli mieleen, että olisikohan asiakas ja kirjaston työntekijät katsoneet ensin vahingossa mobiilikorttia asiakkaan tiedoissa väärältä sivulta esim. asiakkaan Omat-tiedot sivulta. Tiedä häntä, sillä kaikki on mahdollista. :D

**Lumme**
* Kirjeviestien lähettämisessä häiriötilanne 13.2. alkaen. Tilanne huomattu 24.3.
* Tilejä lukkiutunut ja jäljet näyttävät johtavan Ellibsiin.
* 100% pääkäyttäjä aloittaa viikolla 14, Hanna Ikonen.
* Nextin testaus ja säätö jatkuu.

**Siilinjärvi**
* Kunnasta tullut ilmoitus, että verkkomaksaminen on nyt valmis käyttöönottoon. Siirretään sitä versionvaihdon yli, mikäli mahdollista.
* Koska kuljetustilan peruminen Finnassa tuntuu toimivan ongelmitta muuaalla, otetaan se meilläkin nyt käyttöön.
* Jos maa on asiakastiedoissa turhaa tietoa, piilotetaan se pois Kohasta ja Finnasta.

**Helle**
* Asiakkaalla on ollut yksi varaus niteettömään tietueeseen. Kohassa asiakkaan Varaukset-välilehdellä yksikään asiakkaan varauksista ei näkynyt.
* Yksi Sotuteekin käyttäjistä ilmoittanut, että Sotuteekki heittää toiminnosta ulos pikaisesti. Useimmiten yhden haun jälkeen (muutaman minuutin jälkeen). Toisinaan Sotuteekki saattaa pysyä auki vähän kauemmin. 

**Kyyti**
* Haminasta on tiedusteltu tilastojen saamista ulkoiseen järjestelmään ns. johdon työpöydälle. Kohassa ei vielä sellaista ominaisuutta ole. Koha-Suomen strategiassa asia on mainittu. Anneli selvittää vielä, mikä ongelma oli raporttien JSONiin liittyen.

**Lappi**
* Ei mitää erityistä. Versionvaihtoa ja normi ylläpitoa.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-13-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 12 muistio

Aika: 21.3.2023 klo 9.15 <br />
Läsnä: Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi), Pia Kusmin (Lappi), Heli Auranen, Tenho Volanen, Timo Pesonen (Lumme), Anni Rajala (Vaski), Anneli Österman ja Pasi Kallinen (Koha-Suomi)

**Yhteiset**
* Pohdintaan: Meillä säilytetään kimpasta riippuen ei-aktiivisten asiakkaiden tiedot 5-6 vuotta, mutta tiedot poistetaan asiakkaan pyynnöstä jo sitä ennen. Laskut pitää säilyttää lain mukaan 10 vuotta lähdejärjestelmässä. Voiko asiakkaan poistaa, jos häneltä on laskutettu aineistoa alle 10 vuotta sitten poistopyynnön ajankohdasta?
  * Pirkko-Liisa kyseleen Oulun arkistonhallintahenkilöltä tarkempia tietoja. Jatketaan sen jälkeen asian pohdintaa.
* [Koha-klinikka 29.3.2023 klo 9-11](https://github.com/KohaSuomi/Koha/discussions/469). Esitellään uutta versiota.
* [Versionvaihdon tiedote 2](https://github.com/KohaSuomi/Koha/discussions/471)
* [Finna-nextit](https://github.com/KohaSuomi/Koha-22x/wiki/Finna-nextit)
* Maksut-osiossa Tapahtumat-välilehdellä nappien lisäpiilotuksia? Onko Tulosta ja Maksa turhia?<br />
![kuva](https://user-images.githubusercontent.com/33121325/226279846-d976157d-2e54-42bc-9e74-1102cf3c6d5c.png)
  * Reetta tekee tiketin piilotuksista Koha-repositorioon. Anneli tutkii sopivassa välissä, miten piilotukset onnistuu.
* [Varaustunnus asiakasmääreeksi](https://github.com/KohaSuomi/Koha-22x/wiki/Mit%C3%A4-pit%C3%A4%C3%A4-tehd%C3%A4-next-kannassa#varaustunnus-asiakasm%C3%A4%C3%A4reeksi)
* Kohan ohje suomeksi päivitysvastuut, aiemmin näin:
  * Asiakkaat: Piia Semenoff
  * Lainaus: Pirkko Lauhikari
  * Maksut: Lumpeet
  * Varaukset: Lumpeet
  * Kuvailu: Päivi Knuutinen
  * Kausijulkaisut: Vaski
  * Hankinta: Anneli Österman
  * Listat ja Kori: Lappi
  * Raportit: Anneli Österman
  * Tiedonhaku: Kyyti
  * Kuittitulostuksen asetukset: Pirkko-Liisa Lauhikari
  * Työkalut
    * 12.1-12.3 Asiakaslistat - Myöhästymisilmoitusten määrittely: Reetta Pihlaja
    * 12.4. Lähetä laskuja -> tämä pitäis saada pois numeroinnista
    * 12.5-12.10 Asiakkaiden poisto - Tietueiden muokkaus: Lappi (HUOM! osa siirtynyt Kuvailu-osioon)
    * 12.11 Automaattinen niteen muokkaus: Kati Sillgren
    * 12.12 MARC-muokkauksen pohjat: Kati Sillgren
    * 12.13 Kalenteri: Piia Semenoff
    * 12.14 Lokien katselu: Tuomas Kunttu
    * 12.15-12.17 Uutiset-Siirtokokoelmat: Tuomas Kunttu
  * [Kohan ohje suomeksi -muotoiluohjeet](https://github.com/KohaSuomi/kohasuomi.github.io/wiki/Kohan-ohje-suomeksi--muotoiluohjeistus)

Kuulumiset pohjoisesta etelään.

**OUTI**
* Verkkokirjaston Finna-tilin sähköpostikentässä olevaa s-postiosoitetta käytetään mm. verkkomaksujen maksukuittien lähettämiseen, mutta tähän s-postikenttään ei päivity tieto, jos asiakkaan sähköpostiosoite on muutettu Kohan asiakastietoihin tai Finnassa asiakkaan Omat tiedot -osion ”Kirjaston ylläpitämät henkilötiedot -osioon”. Aasiakkaan on itse päivitettävä muuttunut s-postiosoite Finna-tilin kenttään. 
Finna-tuki on ottanut pohdittavakseen, mitä ongelmalle voitaisiin tehdä. Ehdotimme, että Finna-tilin sähköposti-kenttä pitäisi aina päivittyä, jos asiakaan osoite muutetaan Kohaan tai ”Kirjaston ylläpitämät henkilötiedot” -osioon. Toinen vaihtoehto voisi olla, että sähköpostit lähetetään aina siihen osoitteeseen, joka on ”Kirjaston ylläpitämät henkilötiedot” -osiossa. 

**Siilinjärvi**
* Tehty tiketti [#476](https://github.com/KohaSuomi/Koha/issues/476) painikkeiden lisäpiilotuksesta
* Ei muuta erikoista

**Lappi**
* Normi ylläpitoa
* Versionvaihtoon liittyviä töitä

**Lumme**
* Nextin säätöjä tehty, testailu käynnistetään laajemmin.

**Vaski**
* Perusylläpitoa ja Nextin testaamista.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-12-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 11 muistio

Aika: 14.3.2023 klo 9.15 <br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Pia Kusmin (Lappi), Tuomas Kunttu (Kyyti), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Heli Auranen, Timo Pesonen (Lumme), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* Tapahtumalokin (action_logs) aktiivisen taulun datan siivous arkistotauluun kuukausittain. Siivousajo vuositasolla liian raskas. /Lari
* Viesti-cronien ajastukset säännöllisen huoltoikkunan aikavälin ulkopuolelle?
  * Tällä hetkellä on osassa kimppoja ajastettu huoltoikkunan aikavälille (klo 7-9) mm. advance_notices, overdue_notices ja membership_expiry -cronit ja ne eivät tule ajetuksi automaattisesti. 
  * Kaikki cronit on estetty huoltoikkunan ajaksi eli kuukauden toisena keskiviikkona klo 6.50 - 9.10 ei ajeta croneja.
  * **Päätös**: Ajastetaan kaikille kimpoille aina (ei vain huoltoikkunan aikaan) viestien generointi klo 9.11 ja viestien lähetys alkamaan klo 9.30. Ajastus muutetaan 12.4.2023 lähtien.
* https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues/2 Listattujen nidetilojen priorisointi
* [Versionvaihdon testattavien tilanne](https://github.com/orgs/KohaSuomi/projects/6/views/3)
* OAI-PMH saatu toimimaan, joten nyt Anneli voi pyytää testi-Finnat next-kannoille.

Kuulumiset etelästä pohjoiseen.

**Vaara**
* Päivi testannut nextillä hieman, tallentanut asetuksia jne. Pääkäyttäjien yhteinen katselmus vielä tekemättä.
* Testattavien tikettien tutkailu jäi lyhyeen, kun en osannut tarttua moneenkaan tikettiin ymmärryksen puutteen vuoksi.

**Lappi**
* Lapissakin otetiin käyttöön yläpalkin Koha-asioiden alasvetovalikko. Kiitos Helle ja Kati vinkistä.
* Versionvaihtoon liittyviä töitä, mm. asetusten määrittelyä Nextiin. Testaus pyritään alkamaan mahdollisiman pian.

**Kyyti**
* Kansikuvien näkymiseen liittyvään tekemääni [tikettiin](https://bugs.koha-community.org/bugzilla3/show_bug.cgi?id=33193) Bugzillassa on vastattu. 
Sen perusteella asia on liian vaihea korjattavaksi.
* Lähikirjastossa palautettu nide ei ole mennyt kuljetustilaan, vaikka palautettaessa siitä tulee ilmoitus ("Palauta tämä nide kirjastoon X"). Nide näkyy Lähetettävät kuljetuksen -raportilla, mutta ei vastaanottavan kirjaston Vastaanotettavat kuljetukset -raportilla. Silti nide on saatavana-tilassa. Mitään syytä asialle ei löytynyt. Tilanteen saa korjattua, kun ensin vaihtaa kirjautumiskirjaston vastaanottavaksi kirjastoksi ja palauttamalla niteen ja sitten vaihtaa kirjautumiskirjaston takaisin ja paluttaa niteen. Nyt kuljetustila menee päälle.

**OUTI**
* Asiakkaalta oli tullut palautetta, että kun hän kirjautuu mobiililaitteella verkkokirjastoon käyttäen Firefoxia ja hänellä on päällä automaattinen käyttäjätunnuksen ja salasanan täyttöä, PIN-koodi tulee selväkielisenä Kirjaudu sisään -painikkeeseen/painikkeen päälle. Chromella vastaavaa ongelmaa ei tullut. Asiakas oli asentanut Firefoxin uudelleenkin, mutta sekään ei ollut auttanut. Lopulta selvisi, että ongelma tuli asiakkaalla OnePlus Nord 2T 5G -puhelimella. Vika liittyy ilmeisesti valmistajan käyttöjärjestelmään ja selaimeen. Oulun it-tiimi testasi myös muiden valmistajien laitteilla, eikä ongelmaa saatu niissä toistettua.
* Luetteloijilta tuli palautetta, että TäTin nalkutin herjaa 884 5 -kentästä: ”ei formaatissa”. Eli nalkutin tärppäsi kiinni kyseiseen kenttään, koska se ei oikeasti kuulu MARC21-formaattiin. Kentän 884 5-osakenttä on nyt lisätty TäTin nalkuttimeen, joten ei pitäisi herjata siitä enää. Heikkisen Antti on yhteydessä Melindaan 884 5-kentän käytöstä.
*  Toinen Kirjastopalvelun tietuepaketeista, joka oli tullut 7.3., näytti, että se olisi tuotu, mutta tietueita ei löytynyt TäTistä. Anneli poisti paketin tuonnin ja toi sen uudestaan. Paketin sisältämät tietueet alkoivat löytyä saman tien TäTistä. Tietueet olivat tulleet tietokantaan jo ensimmäisen tuonnin yhteydessä, mutta Anneli arveli, että ne eivät olleet jostain syystä indeksoituneet.
*  Nexstiä säädetty. Yhdessä katsottu, mitä otetaan käyttöön uusista ominaisuuksista, IntranetuserCSS:n ja -JS:n vapaaehtoisista määrityksistä.

**Lumme**
* Nextin säätäminen aloitettu
* Otetiin käyttöön yläpalkin Koha-asioiden alasvetovalikko heti viime viikon kokouksen jälkeen, kiitos vinkistä.

**Siilinjärvi**
* Nextin tutkailu ja säätäminen aloitettu täälläkin.
* Siilin muista poikkeavat croni-ajastukset voidaan yhtenäistää muiden kimppojen kanssa.
* Muuten ei erikoista.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-11-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 10 muistio

Aika: 7.3.2023 klo 9.15 <br />
Läsnä: Leena Kinnunen, Pia Kusmin (Lappi), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Kati Sillgren (Helle), Heli Auranen, Katja Valjakka (Lumme), Päivi Knuutinen (Vaara), Tuomas Kunttu (Kyyti), Reetta Pihlaja (Siilinjärvi)

**Yhteiset**
* [Finna-liitännäisen Readme-osioon](https://github.com/KohaSuomi/koha-plugin-rest-di/blob/master/README.md#sysprefs) kerätty, mitä järjestelmäasetuksia Finna-liitännäinen hyödyntää.
* Kuvailupohjissa Hinta voimassa alkaen ja Hankintapvm ei-pakollisiksi.
  * Hinta voimassa alkaen (replacementpricedate) ei kannata olla pakollinen, koska silloin siihen on pakko kirjoittaa jotain ja siihen tulee myös arvoja 0000-00-00, joista [Finna ei tykkää](https://github.com/KohaSuomi/Koha/issues/280). Kenttä täyttyy automaattisesti tallennuspäivällä, kun kenttä ei ole pakollinen.
  * Hankintapvm (dateaccessioned) täyttyy myös automaattisesti, kun siihen on kuvailupohjassa liitetty dateaccessioned-pl-liitännäinen. Ei ole tarvettaa laittaa pakolliseksi kuten datereceived aikanaan.
  * Päätös: otetaan pois kenttien pakollisuus. Pääkäyttäjien tehtävä muutos manuaalisesti kuvailupohjiin tuotantoon ja nextiin.
* Mitä tietoja tarvitsee siirtää nextiltä tuotantoon versonvaihdon aikaan. Edellisessä versionvaihdossa kerättiin [tällaista listaa](https://tiketti.koha-suomi.fi/projects/mls/wiki/P%C3%A4%C3%A4k%C3%A4ytt%C3%A4j%C3%A4t_-_vuosi_2022#Viikko-21-muistio).
  * järjestelmäasetukset
  * kuittipohjat
  * asiakasrajoitukset?
  * asiakasmääreet?
* IntranetNav-järjestelmäasetuksessa olevat linkit ajantasalle. Jos linkkejä vielä Redmineen, päivitättehän ne ohjaamaan GitHubiin vastaaville sivuille.
* Onko tarvetta omalle kanavalle versionvaihdolle Matrixiin?
* next-kannat
   * [mitä pitää muistaa tehdä next-kannassa](https://github.com/KohaSuomi/Koha-22x/wiki/Mit%C3%A4-pit%C3%A4%C3%A4-tehd%C3%A4-next-kannassa) 
   * finnat, Anneli pyytää kaikille, kunhan Kirkesin next olemassa
   * kaikki muut paitsi kirkes olemassa

**Lappi**
* Lapin pääkäyttäjät lomalla 10.3., ei päivystystä
* Nextiin viety asetuksia. Jaettu Käyttäjäryhmälle ja pääkäyttäjille testivastuita. 
* Otettu käyttöön uusia asetuksia: Nidetunnus varauksen saapumisilmoitukseen, Tiettyjen teosten valinta tarkempaan tarkasteluun, 
Epäonnistuneiden kirjautumisyritysten aktiivinen seuranta, Asiakaslajien viestiasetusten oletusruksit poistettu. 
* Kysy Kohasta pidetty onnistuneesti, käsiteltiin mm. tiedonhakua ja käyttäjiltä Padletilla kerättyjä kommentteja ja ongelmia. Päätetty järjestää jatkossa kaksi kertaa vuodessa. 

**OUTI**
* Uuden version uudet järjestelmäasetukset, IntranetUserCSS:t ja JS:t käyty läpi Annelin suositusten mukaan. Testaajia pyydetty henkilökunnasta.
* Otettu käyttöön Finnan ominaisuus, että asiakas voi perua itse kuljetettavana olevan varauksensa. 
* Nyt Celiat näkyvät Kirja-aineistotyypin alatyypeissä Äänikirja, joka jää faseteissa isojen tulosten kohdalla näkymättömiin. Piia kysynyt Finna-tuesta, olisiko mahdollista, että Kirja-valikko aukeaisi siten, että Äänikirja-aineistotyyppi näkyisi aina heti asiakkaalle hakutulosten määrästä riippumatta. Finna-tuki vastasi, että ei onnistu.
* Oulussa Puolivälinkankaan kirjasto menee remonttiin ja suljetaan 6.4.2023. Kirjaston kokoelma siirretään Koskelan kirjastoon, joka on ollut pitkään kiinni ja kirjastolle on nyt löytynyt väistötilat. Koskelan kirjasto avataan kesällä.

**Lumme**
* Automaateissa ongelmia. Palautusautomaatti ihan jumissa ja lainausautomaatit pätkivät. Sip palvelin käynnistetty uudelleen ja Lyngsoe käynnisti ohjelmat uudelleen. Lopulta lähti toimimaan.

**Vaara**
* Ei erityisempää. Päivi testannut nextiä ja käynyt läpi järjestelmäasetukset Annelin listauksen mukaan. Muut pääkäyttäjät eivät ole ehtineet juurikaan testaamaan ja yhteinen palaveri järjestämättä.
* Päivi testaillut PowerBIn raportteja ja toimintaa.

**Kyyti**
* Kyytissä lapsiasiakkaan yläikäraja on ollut 15 vuotta. Ja henkilöasiakkaan alaikäraja niin ikään 15 vuotta. Tästä seuraa se, että 15-vuotiaan voi tallentaa sekä lapsi- että henkilöasiakkaana. Jos tallentaa lapsena, muuttaa croni kyllä seuraavana yönä henkilöasiakkaaksi.
Näin asetuksen kuuluukin olla, jotta croni toimii oikein.
* Mitä kuuluu tiketille [#204](https://github.com/KohaSuomi/Koha/issues/204)? - on edelleen työn alla, joten ei vielä kuulukaan tuotannossa toimia.

**Siilinjärvi**
* Ei erityisempää, yritetään päästä kärryille nextin testaamisesta
* Sähköpostit kulkevat hyvin uudella noreply-osoitteella. Paitsi kuittiteksteihin unohtui vaihtaa meidän oma vanha kirjasto(at)siilinjarvi.fi, nyt vaihdettu.
* Kirjautumisyritys-asetukset pitäisi nyt olla meilläkin kunnossa.
* Luettelointipohjien ei-pakollisuudet päivitetty tuotantoon ja nextiin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-10-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 9 muistio

Aika: 28.2.2023 klo 9.15 <br />
Läsnä: Anneli Österman ja Kodo Korkalo (Koha-Suomi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Veli-Pekka Marjoniemi (OUTI), Kati Sillgren (Helle), Anni Rajala (Vaski), Leena Kinnunen (Lappi), Reetta Pihlaja (Siilinjärvi), Heli Auranen, Timo Pesonen (Lumme)

**Yhteiset**
* [Ajastetut ajot](https://koha-suomi.fi/dokumentaatio/ajastetutajot/) kuvattu ohjeisiin ja esittelyvideo [Crontabista](https://PPwww.youtube.com/watch?v=otIk2KIWPxM) Youtubessa.
* [Maksut sähköpostikuittiin](https://tiketti.koha-suomi.fi/issues/4245)
* Tiketti [KohaSuomi/Koha #204](https://github.com/KohaSuomi/Koha/issues/204) - kaikilta pois oletusviestiasetukset?
  * Sovittiin, että kaikki ottaa pois oletusviestiasetukset, koska jos käyttäjä unohtaa ottaa rastit pois, ei ne poistu tiketissä luodulla JS-rimpsulla ja tiketin alkuperäinen ongelma jatkuu.
* Ei päivitettävää vkolla 9
* Vkolla 10 säännöllinen huoltoikkuna
  * tulossa käyttöjärjestelmäpäivityksiä, mahdollisesti pieniä katkoja, jos palvelimet joudutaan käynnistämään uudelleen. 

**Vaara**
* Pyydetty Finnatukea laittamaan päälle asetus, jonka mukaan asiakas voi peruuttaa kuljetettavana olevan varauksen Finnan kautta. Tiedotettu henkilökuntaa asiasta eikä ole tullut ihmettelyä.
* Vaaran next-kannan testausta. Ulkoasu ei ole ihanteellinen huonoine kontrasteineen ja pienine fontteineen. Pitää testata zoomauksen kanssa, miten vaikuttaa näkymiin ja ryhtyä testaamaan myös tikettien mukaisia toimintoja.
* Itsepalvelulainaus tarkoitus laittaa päälle huomenna Kiihtelysvaaran kirjastossa. Kirjautumisongelman syy on selvinnyt (siivousajo) ja se korjataan vasta versionvaihdon jälkeen, joten siihen saakka mennään nykyisellä "virityksellä".

**OUTI**
* Kuljetettavana olevan varauksen peruminen testi-Finnassa:
  * Testeissä ei ongelmia.
  * Kysytty muilta OUTI-kirjastoilta mielipidettä, ne ketkä ovat jo kommentoineet ovat todenneet hyväksi muutokseksi.
* Muuten normaalia tukityötä.

**Helle**
* Lasse lisännyt niteet Porvoon niteettömille artikkeli-tietueille https://github.com/KohaSuomi/Koha/issues/419
* Emmi perunut tietueettomat tilaukset https://github.com/KohaSuomi/Koha/issues/452
* Emmi poistanut vanhat, kevään 2022 epäonnistuneet EditX-sanomat https://github.com/KohaSuomi/Koha/issues/453
* Lisätty maksut näkymään lainaus-sähköpostikuitille ja palautus-sähköpostikuitille Annelin ratkaisulla https://tiketti.koha-suomi.fi/issues/4245

**Vaski**
* Turun pk:n tunneloidut palautusautomaatit lakanneet toimimasta 27.2. iltana. Vian selvittelyä jatketaan, mukana Bittiguru ja Turun tietoliikenne.

**Lappi**
* Rauhallista.
* Tänään Kysy Kohasta -webinaari Lapille: ohjeita, vastauksia ongelmiin ja ärsyttäviin ominaisuuksiin, vinkkejä, teasereita.

**Siilinjärvi**
* Vaihdettu tänään sähköpostiviestien lähettäjäksi noreply@koha-suomi.fi
* Oletusviestiasetusten poisto ei aiheuta meillä ongelmia, tekstiviestitäpät poistettu ja tiedotettu henkilökuntaa, sähköpostitäppiä ei ollutkaan.
* Kuljetustilan poisto Finnassa kiinnostaa myös meitä, työn alle.

**Lumme**
* Oletusviestiasetuksista poistettu valmiit täpät

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-9-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 8 muistio

Aika: 21.2.2023 klo 9.15 <br />
Läsnä: Leena Kinnunen, Pia Kusmin (Lappi), Päivi Knuutinen ja Auli Rantasalo (Vaara), Tuomas Kunttu (Kyyti), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Kati Sillgren (Helle), Susanna Sandell (Vaski), Heli Auranen, Katja Valjakka, Timo Pesonen (Lumme)

**Yhteiset**
* Asiantuntijatyöryhmän kokouksesta
  * stafflogininstructions-järjestelmäasetukseen muistutus kirjaston valinnasta, jos työskentelee useammassa toimipisteessä. [Redmine-tiketti #4467](https://tiketti.koha-suomi.fi/issues/4467)
  * [Varausten oletusvoimassaoloaika kolmeen vuoteen.](https://github.com/KohaSuomi/Koha/issues/451)
* Mikä sms-operaattori käytössä?
  * Lappi: Link Mobility
  * OUTI: Link Mobility
  * Siili: Link Mobility
  * Vaara: Link Mobility
  * Lumme: Link Mobility
  * Kyyti: Arena Interactive
  * Helle: Telia
  * Vaski: DNA
* [Redmine-tiketti #4461](https://tiketti.koha-suomi.fi/issues/4461) - onko kommenteissa vielä jotain sellaisia toiveita, joita ei nykyään vielä ole? Jos on, teettekö niistä uudet tiketit tarvittaessa GitHubiin.
* [Ratkaisu ehdotettu -tiketit](https://github.com/orgs/KohaSuomi/projects/4/views/15)
  * 505 - Lapin testaus puuttuu vielä?

**Lappi**
* Rauhallista, valmistaudutaan omaan Kysy Kohasta-webinaariin
* Käyttäjäryhmä aktivoitu, saatu pari jäsentä lisää. 

**Vaara**
* ei mitään erityistä mainittavaa

**Kyyti**
* Kysyin tekstiviestien tuplaviestien poistamisesta. Ominaisuus on siis Kohan yhteisökoodissa.
* Redminen tiketti [#1849](https://tiketti.koha-suomi.fi/issues/1849) vaatisi edelleen huomiota. Anneli ottaa asian esille.
* Olen kirjoittanut tikettiä yhteisön Bugzillaan [#5303](https://tiketti.koha-suomi.fi/issues/5303) ja pyysin että joku kokeneempi katsoisi tekstin vielä läpi.

**OUTI**
* Rauhallista tukityötä.
* Versionvaihdon testaustaulukon kaikki osa-alueet käyty alustavasti läpi.

**Helle**
* Porvoon tunneloidulla palautusautomaatilla oli pakollinen käyttökatko 8.-15.2.2023. Automaatti kuormitti palomuuria muodostamalla jatkuvasti uusia (satoja) yhteyksiä. Tunnelointi rakennettu uudestaan. Tähän osallistuivat: palvelinsalin operaattori, Porvoon IT, Telia.

**Vaski**
* Pohdittiin viestipohjien testausta next-ympäristössä. Testaus todettiin tarpeelliseksi.
* Varausjono-raportin testaustuloksia kaivattiin.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-8-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 7 muistio

Aika: 14.2.2023 klo 9.15 <br />
Läsnä: Anni Rajala (Vaski), Mikko Liimatainen (Vaski), Susanna Sandell (Vaski), Anneli Österman ja Lari Strand (Koha-Suomi), Kati Sillgren (Helle), Tuomas Kunttu (Kyyti), Heli Auranen, Timo Pesonen (Lumme), Reetta Pihlaja (Siilinjärvi), Pia Kusmin (Lappi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Pirkko-Liisa Lauhikari (OUTI)

**Yhteiset**
* Käydään läpi uuden version [uudet ominaisuudet](https://github.com/KohaSuomi/Koha-22x/wiki/Uutta) -listaus. Tallennetaan tämä osio. [Tallenne uusien esittelystä](https://www.youtube.com/watch?v=IUophuEubSM)
* Idea: kerran kuussa esim. klo 13-15 _Bugi-perjantai_, jossa testataan ja sign offataan meille tärkeitä ominaisuuksia/tikettejä. Aloitus versionvaihdon jälkeen. Emmi lupautunut kehittäjistä mukaan, testaajiksi pääkäyttäjiä.
* [Viikon 7 päivitys](https://github.com/KohaSuomi/Koha/discussions/432)
* next-kantojen tilanne
  * datan redusointiskripti melkein valmis
  * ensin tehdään Vaara Annelin pyynnöstä, sitten muut
* [Kohan ohje suomeksi -muotoiluohjeistukset](https://github.com/KohaSuomi/kohasuomi.github.io/wiki/Kohan-ohje-suomeksi--muotoiluohjeistus) tehty. Ohjeita voi noudattaa jo nyt, mutta viimeistään silloin, kun päivitetään ohjeet uutta versiota vastaavaksi.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-7-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 6 muistio

Aika: 7.2.2023 klo 9.15 <br />
Läsnä: Reetta Pihlaja (Siilinjärvi), Tuomas Kunttu (Kyyti), Christer Skog (Kyyti), Kati Sillgren (Helle), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Anneli Österman ja Kodo Korkalo (Koha-Suomi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Susanna Sandell (Vaski), Heli Auranen, Timo Pesonen (Lumme), Leena Kinnunen (Lappi)

**Yhteiset**

* Vuosi vaihtunut, onko [Integraatiot-lista](https://github.com/KohaSuomi/Koha/wiki/Integraatiot) ajan tasalla?
* Koha-Suomen nettisivuille siirretty
  * [Tietoturvaohje](https://koha-suomi.fi/dokumentaatio/tietoturvaohje/)
  * [Tietojen säilytysajat](https://koha-suomi.fi/dokumentaatio/tietojensailytysajat/)
* Ei viikkopäivitystä, koska ei ollut päivitettävää
* Keskiviikkona säännöllinen huoltoikkuna, jolloin vaihdetaan palomuurin muistikampoja. Ei pitäisi aiheuttaa katkoksia.
  * Voi vaikuttaa tunneloituihin automaatteihin
* [Finna-kehitysehdotusten](https://github.com/KohaSuomi/Finna-kehitysehdotukset/issues) läpikäynti /Susanna
  * Käytiin läpi kolme ehdotusta ja kirjattiin niihin päätökset.
* [Lapin, OUTIn ja Vaskin action_logs-taulujen korjaukset](https://github.com/KohaSuomi/Koha/issues/403) aiheuttaa viivettä tietojen replikoinnissa masterilta slaveen.

**Siilinjärvi**

* Mikro-Väylä päivittänyt loputkin automaatit viikolla 4 ja lisännyt asetuksiin Sipinstitution id:t
* Ei muuta

**Kyyti**
* On selvitelty ongelmaa, jossa asiakkaalla oli lainassa kirjoja, joita hän ei ollut lainannut. Selityksenä vaikuttaisi olevan, että hänen jälkeensä automaatille tulleen lainaukset ovat kirjautuneet hänen kirjastokortilleen.
* Tehty tiketti [#404 Noutamattoman varauksen määräytyminen nidetyypin mukaan](https://github.com/KohaSuomi/Koha/issues/404)

**OUTI**
* Oulun Finvoice-laskutusprojekti saatu toivottavasti nyt valmiiksi.
* Tuplaverkkomaksuja tulee yhä. OUTIsta laitettu ongelmasta palautetta myös Finna-tukeen. Palautteeseen laitetiin pari esimerkkiä, joissa asiakkaan ja maksun tiedot, tuplamaksujen pvm ja kellonajat.

**Helle**
* Pornaisten kirjaston tunneloitu automaatti poistettu käytöstä. Uusi käyttöön otettu automaatti toimii tietoturvallisesti ilman tunnelointia.

**Vaara**
* Lehtitietueisiin ryhdytty lisäämään luokka, jotta saadaan signumit oikeanlaiseksi.
* Viime viikon keskiviikkona iski hetkellinen paniikki, kun tiketin 232 (Vanhat omatoimikäytön estoblokit tulisi ajaa pois päältä) ajo oli tehty. Vaarassa se tarkoitti kaikkien omatoimikäytön estoa, koska Toveri käyttää tätä toimintoa sallimaan sisäänpääsyn. Onneksi tilanne saatiin nopeasti korjattua, kun huomasin asian.
* Itsepalvelulainaukseen tehty muutos otettu testaukseen, toivottavasti kirjautuminen onnistuu sen myötä.

**Vaski**
* Ei uutta

**Lappi**
* Tätistä valui Celia-tietue valui 6 väärän tietueen päälle, koska TäTin tietueella oli 020a-kentässä tallennettuna
tyhjä välilyönti joka löytyi myös näistä tietueista.

* Tornion asiakas on saanut Finnassa uusiessa lainalle eräpäivän Tornion kiinniolopäivälle.
Remontin takia eräpäivät on muutettu, ja niihin on tulossa vielä uusi ajo.

* OKM-tilasto ajetaan vielä uudelleen, koska Yhteispohjoismaisen auton osalta tarvitaan "autoittain" eriteltynä.
Nyt koottu OKM-ryhmiksi, joista ei saa eri kuntien osalta tuloksia. Tehdään "auto"-kohtaiset ryhmät ja ajetaan OKM uudelleen.

* Kysy Kohasta Lapille 28.2. : kerätty kysymyksiä ja kommentteja Padletilla henkilöstöltä.

* Redminen omat tiketit osittain läpikäymättä, yritetään ennättää hoitaa kuntoon.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-6-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 5 muistio

Aika: 31.1.2023 klo 9.15<br />
Läsnä: Leena Kinnunen, Pia Kusmin (Lappi), Heli Auranen, Tenho Volanen, Timo Pesonen (Lumme), Päivi Knuutinen ja Auli Rantasalo (Vaara), Veli-Pekka Marjoniemi ja Pirkko-Liisa Lauhikari (OUTI), Anneli Österman ja Emmi Takkinen (Koha-Suomi), Kati Sillgren (Helle), Reetta Pihlaja (Siilinjärvi, paikalla yhteisten asioiden ajan), Mikko Liimatainen (Vaski)


**Yhteiset**
* [Vkon 5 päivitys](https://github.com/KohaSuomi/Koha/discussions/396)
* [Versionvaihtoon keskittyminen](https://github.com/KohaSuomi/Koha/discussions/395)
* [Onko tiketti Koha #311 ok kaikilla?](https://github.com/KohaSuomi/Koha/issues/311)
* Onko kaikki tarkistanut indeksin toimivuuden [tiketin 213](https://github.com/KohaSuomi/Koha/issues/213) muutoksen jälkeen?
* Miten olisi helpointa seurata työn valmiusastetta silloin, kun sama työ tehdään kaikille kimpoille? [Yksi ehdotus](https://github.com/KohaSuomi/Koha/issues/213#issuecomment-1405045158).
  * Ehdotus ei toiminut, koska pääkäyttäjien write-oikeuksilla ei pysty muokkaamaan toisten kommentteja.
  * Emmi löysi ohjeen [GitHubin Task-toimintoon](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/about-task-lists)
  * Sovittiin, että tehdään seuranta niin, että Anneli/joku muu lisää yhden kommentin, jossa tehdään seuranta. Kun asia on omassa kimpassa ok, yksi kimpan pääkäyttäjistä käy peukuttamassa kommenttia, jolloin peukkujen määrästä voi päätellä, onko kaikki tehty.
  * Anneli testaili vielä kokouksen jälkeen ja yhdisti peukutuksen Task-toimintoon näin: ![kuva](https://user-images.githubusercontent.com/33121325/215745423-71572ea9-a647-411e-89d1-659e821de834.png)
  * Anneli tai joku muu admin käy lisäämässä raksit peukkujen perusteella kommenttiin.
* Kun versionvaihdon next-kannat saadaan käyttöön, mitä kantaa Anneli saa käyttää esim. IntranetUserCSS:ien ja IntranetUserJS:ien testaamiseen?
  * Vaara ilmoittautui vapaaehtoiseksi
  * Anneli päivittää [Järjestelmäasetukset-sivulle](https://koha-suomi.fi/dokumentaatio/jarjestelmaasetukset/), mitkä rimpsut toimivat versiossa 22.11.
* Bugin tekeminen yhteisön [Bugzillaan](https://bugs.koha-community.org/bugzilla3/).
  * Rekisteröidy
  * [Yhteisön raportointiohjeistus](https://wiki.koha-community.org/wiki/Bug_Reporting_Guidelines)
  * [Bugzillan ohje tiketin tekemiseen](https://bugzilla.readthedocs.io/en/5.2/using/filing.html#reporting-a-new-bug)
  * [Koha-yhteisön sandboxit](https://wiki.koha-community.org/wiki/Sandboxes)
* Kohan ohje suomeksi - Asiakkaat -> [Rajoitukset-osioon](https://koha-suomi.fi/dokumentaatio/asiakkaat/#1510-rajoitukset) lisätty Tili lukittu ja rajoite moninaisista epäonnistuneista kirjautumisyrityksistä
  * Pirkko-Liisa lisää vielä linkin Lainaus-osiosta näihin ohjeisiin.
* [Nideryhmät versiossa 22.11](https://github.com/KohaSuomi/Koha-22x/wiki/Uutta#nideryhm%C3%A4t) - otetaanko käyttöön ja pyydetäänkö Finnaankin?
  * Toimintoa pidettiin hyvänä, varsinkin jos siihen saadaan yhdistettyä Koha-Suomen tekemänä triggereitä ja ajoa, jotka luovat nideryhmät automaattisesti kausijulkaisutilausten perusteella ja vievät enumchronin perusteella niteet oikeaan nideryhmään.
  * Kysytään Finna-toimistosta, saisiko Finnaankin tuen ainakin varausten tekemiseen. 
  * 
**Lappi**
* Tukipostissa rauhallista
* Koha-käyttäjäryhmän kokous pitkästä aikaa. Päätettiin asetusten käyttöönotosta, osa jo ed. versiopäivityksessä tulleita ominaisuuksia, osa Kirkes-järjestelmäasetusten läpikäynnissä esille tulleita asioita. 
* Tornion kirjasto suljetaan jo ensi viikolla. Muut kirjaston sulkutoimet saatu tehtyä, mutta ongelmana varausten keskeyttäminen ja noutopaikan estäminen, koska ei ole toista toimipistettä, joka voitaisiin Finnassa osoittaa noutopisteeksi. 

**Lumme**
* Uudet OKM tilastot ajettu 30.1.2023
* Lumpeilla jäänyt viestiasetusten defaultteihin sähköposti, jolloin sähköpostikohtiin on tullut täpät myös niille asiakkaille, joilla asiakastiedoissa ei ole sähköpostia. Tästä johtuen on tullut paljon epäonnistuneita viestejä. Tehtäneen massa-ajo, jolla saadaan asiakkaiden asetukset kohdalleen.

**Vaara**
* Kehuja viime viikon päivityksestä eli hyllyvarauslistan sijaintikirjaston korostuksesta. Kuulemma paras muutos aikoihin :)
* ei mitään muuta erityistä mainittavaa

**OUTI**
* Finna-tuesta on tullut vastaus, että varauksen oletusvoimassaoloaika voidaan muuttaa Koha-ajurin asetuksissa. Asiasta lisää asiakaswikissä: https://www.kiwi.fi/display/Finna/Koha-ajurin+asetukset#Kohaajurinasetukset-Varaukset. Oletusvoimassaoloajan muuttaminen kolmeen vuoteen käsitellään seuraavassa asiantuntijatyöryhmän kokouksessa.
* Oulun Finvoice laskutuksessa vielä ongelmana, että niteen viivakoodi ja nidetyyppi saataisiin näkyviin laskulle. Aluksi tiedot olivat ArticleName-tägissä, mutta tägin merkkimäärä ei saa ylittää 100 merkkiä ja jossain tapauksissa näin käy. ArticleDescription-kenttä ei välity laskulle. Nyt Monetralta ovat ehdottaneet, että tiedot laitettaisiin RowFreeText-elementtiin. Testaukset jatkuvat.
* Varauksen tekosivulle lisätty ohjeteksti, kun tehdään nidevaraus: "Valitse noutokirjasto niteen kohdalta, jos teet nidevaruksen". Tekstin voi lisätä CSS:llä. Ohje Redminen tiketissä #5475.

**Kyyti**
* Päivitin uuden tarratulostustiedon Koha-Suomen käyttöohjeisiin https://koha-suomi.fi/dokumentaatio/tyokalut/#12164-tarratulostusty%C3%B6kalu
* Siirtoraportissa oli jotain häikkää, mutta se oikeni päivän kuluessa.

**Helle**
* Porvoon Kerkkoon kirjaston lainoille on tullut lainojen eräpäiviksi kirjaston kalenteriin tallennettuja kiinniolopäiviä. Tämä johtui siitä, että Kerkkoon kirjastosta on lainattu niteitä, joiden sijainkirjasto ei ole ollut Kerkkoon kirjasto. Lainauksessa käytetään niteen sijaintikirjaston kalenteria. Tiketti https://github.com/KohaSuomi/Koha/issues/273 (Tiketissä https://tiketti.koha-suomi.fi/issues/5452 tarkemmin asetusten circcontrol JA homeorholdingbranch arvoihin liittyen.)

**Siilinjärvi**
* Ei mainittavaa.

**Vaski**
* Uuden version testausta aloitellaan
* Tarve saada kuiteille takemmat nimeketiedot. Nämä löytyvätkin nykyään biblio subtitle, part_number ja part_name -kentistä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-5-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 4 muistio

Aika: 24.1.2023 klo 9.15<br />
Läsnä: Anneli Österman, Kodo Korkalo, Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI), Reetta Pihlaja (Siilinjärvi), Heli Auranen, Katja Valjakka (Lumme), Kati Sillgren (Helle), Mikko Liimatainen (Vaski), Leena Kinnunen, Pia Kusmin (Lappi) 

**Yhteiset**
* [Viikon 4 päivitys](https://github.com/KohaSuomi/Koha/discussions/381)
* OKM-tilastot suurimmalla osalla kunnossa. Osalla kimpoista/kirjastoista on vielä isoja määriä virheellisiä signumeita ja cn_sort-tietoja, jolloin kirjojen jako kauno/tieto-akselilla menee väärin.
  * Näiden etsimiseen ei ole kunnollista raporttia, mutta raportilla [Niteet, joiden cn_sort-kenttä alkaa kirjaimella](https://tiketti.koha-suomi.fi/projects/koha-suomen-dokumentaatio/wiki/Valmiita_SQL-raportteja#Niteet-joiden-cn_sort-kentt%C3%A4-alkaa-kirjaimella) voi selailla todennäköisesti virheellisiä.
* [Häiriö- ja huoltotiedotteet](https://github.com/KohaSuomi/Koha/discussions/categories/huolto-ja-h%C3%A4iri%C3%B6tiedotteet) vastaisuudessa GitHubin discussionsiin omana "aihealueenaan".
* Outlook/Hotmail,complainttaavat asiakkaat, lähtevän postin palvelimen "maine" ja viestien perillemeno / Kodo
  * Microsoftin sähköpostiohjelmissa on jonkinlainen "complain" nappi (en tiedä tarkkaan nimeä, koska minulla ei ole käytössä Microsoftin sähköposteja). Tämän napin painaminen kirjastosta tuleen sähköpostiviestin kohdalla aiheuttaa sen, että viestistä lähtee roskaposti-ilmoitus Microsoftille. Napin painamisesti tulee myös ilmoitus lähettävän palvelimen ylläpitäjälle, eli tässä tapauksessa konesalioperaattorille.
  * Tällaisia "complaitteja" on operaattorin mukaan tullut lähes 800 kappaletta ja ongelma on, että suuret määrät "complaintteja" aiheuttaa konesalioperaattorin lähtevän postin palvelimelle mainehaittaa. Viestien perillemeno hankaloituu ja viestit tulevat luokitelluksi esimerkiksi roskapostiksi tai jäävät kokonaan menemättä perille. Ongelma koskee kaikkien Koha-Suomi kirjastojen lisäksi myös kaikkia muita konesalioperaattorin asiakkaita, jotka käyttävät samaa lähtevän postin palvelinta.
  * Oletuksena oli, että asiakkaat ovat kenties olleet siinä käsityksessä, että "complain" napin painaminen välittyy kirjastojen tietoon ja asiakkaat ovat voineet luulla, että kirjastojen viesteistä pääsee halutessaan tällä tavalla eroon. Näin ei siis kuitenkaan ole, vaan tieto "complaintista" tulee ainoastaan konesalioperaattorille ja Microsoftille. Se ei tule Koha-Suomelle eikä kirjastoille.
  * Ajatus oli lähettää operaattorin palvelimelta "complain" nappia painaneiden asiakkaiden sähköpostiin automaattivastaus, jossa asiakasta olisi ohjeistettu tekemään haluamansa muutokset viestiasetuksiin Finnassa ja neuvottu myös tarvittaessa lisäämään kirjastojen viestien lähettäjä luotettujen lähettäjien listalle. Näyttää kuitenkin siltä, että "complaint" syntyy ainakin joissain tilanteissa jollain tapaa automatisoidusti ja ilman asiakkaan toimenpiteitä, joten automaattivastauksen lähettäminen ei tunnu tarkoituksenmukaiselta.
  * Konesalioperaattori toimittaa listan sellaisten asiakkaiden sähköpostiosoitteista, joiden sähköpostista on lähtenyt "complaint" ja kirjastojen kanssa yhteistyössä sitten voidaan tarvittaessa kontaktoida näitä asiakkaita ja ohjeistaa kirjastojen viestien kanssa toimimisessa.
* Sanaston tilastoajot tehty ja toimitettu

**OUTI**
* Raahen ensimmäiset Finvoice-testilaskut lähetetty Kohasta CGI:n edustapalvelimelle, josta laskujen pitäisi siirtyä Rondoon Siirinetin avulla.
* Oulun aineistovalitsijat ovat pyytäneet, että saisiko hankintaportaalin sanomasta Kohaan tiedon, onko tilattu nide muovitettu vai muovittamaton. Woimalta ovat ilmoittaneet, että heidän puoleltaan tämä onnistuu. Kysytty valitsijoilta, mihin tieto halutaan näkyviin: hankinnan tilausrivin huomautuksiin vai pitäisikö olla nidekohtainen tieto? Jos nidekohtainen tieto, missä sen pitäisi Kohassa näkyä? Pitääkö tiedon olla jotenkin haettavissa? Asia vielä siis selvityksessä.
* Lisätäänkö varausten oletusvoimassaoloaikaa vuosi lisää eli kahdesta vuodesta kolmeen vuoteen? Kukaan ei vastuanut ehdotusta. Pirkko-Liisa kysyy Finna-tuesta, onko lisäys mahdollista Finnassa ja viedään sittten päätettäväksi asiantuntijaryhmään.
* Myös OUTIsta ollaan yhteydessä Finna-tukeen tuplaverkkomaksuongelmasta. Vaarasta Päivi on ollut jo yhteysessä ongelmasta, mutta saanut vähän ynseän vastauksen, että hieman hankala tutkia ja ottaa kantaa, mitä tuplamaksutilanteissa on tapahtunut. Jos Finnan verkkomaksu mahdollistaa maksutapahtuman aloittamisen kahteen kertaan, se pitäisi estää.

**Siilinjärvi**
* Otetaan siirtyminen noreply(at)koha-suomi.fi -viestiosoitteeseen työn alle. Tarkistettiin, että muutos tehdään kirjastoasetuksiin https://koha-suomi.fi/dokumentaatio/asetukset/#1-kirjastot
* Edellisen viikon muistiosta bongattu Haminan kuntaäppi. Siilissä Geniemin kuntaäppi (kirjastokortti + "kevyt" verkkokirjasto) on ollut käytössä noin 3 kk, ja palaute asiakkailta on ollut myönteistä.

**Lumme**
* Okm tilastoraportti ei vielä kunnossa. Varkaudessa signumit väärässä järjestyksessä ja myös muissa kirjastoissa useita väärin tehtyjä signumeita. Kehittäjät yrittävät oikaista.
* Vaihto Noreply-viestivastauksiin mennyt tähän asti hyvin. Kaksi kirjastoa vielä vaiheessa.

**Helle**
* Passiiviset Koha-käyttäjät kirjautuvat nyt automaattisesti ulos aiempaa nopeammin, eli Kohan automaattisen aikakatkaisun aikaa on lyhennetty.
* Ei lainata -nidetilan popuptekstien suurennos on otettu käyttöön.
* Hae tietokannasta -hakuun on otettu käyttöön valmiit valittavat hakukentät.
* Hae asiakkaita -hakuehdoksi on lisätty Matkapuhelin. Lajittelu-hakuehdot on piilotettu käytöstä.
* Asiakastiedon asiakkaan tietoruutu on laitettu näkyville (osoitetiedot eivät näy).
* Asiakaspalvelussa on tullut vastaan asiakastieto (ID 15510), jolle on jäänyt muodostumatta lainan (ep. 4.10.2022) 1. myöhästymisilmoitus 12.10.2022. Kyseisen päivän aamuna on ollut Koha-palvelimien huoltokatko. 

**Vaski**
* Anni tarkistanut Mikroväylän automaattien maksujen erotinmerkin. SipFeesDecimalSeparator asetukseen tulee laittaa piste, jotta maksut tulostuvat kuitille oikein.
* Asiakastietojen inforuutuun toivottaisiin tarkennusta "Tili on lukittu" tekstille. Tekstiin voisi laittaa tiedon liian monesta kirjautumisyrityksestä, mikäli tuota ei käytetä muuhun. Myös ohjeisiin selitys kirjautumisyritysten aiheuttamista lukituksista ja rajoituksista.

**Lappi**
* Rauhallista, ei kummempaa

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-4-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 3 muistio

Aika: 17.1.2023 klo 9.15<br />
Läsnä: Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Anneli Österman, Emmi Takkinen, Tuomas Kunttu (Kyyti), Kati Sillgren (Helle), Pia Kusmin ja Leena Kinnunen (Lappi), Heli Auranen, Katja Valjakka (Lumme), Mikko Liimatainen (Vaski), Pirkko-Liisa Lauhikari ja Veli-Pekka Marjoniemi (OUTI)

**Yhteiset**
* Kohan ohje suomeksi -muotoilujen yhtenäistäminen?
  * työryhmä miettii yhtenäiset muotoiluohjeet: Päivi, Tuomas, Anneli
  * jos joku vielä haluaa mukaan, ilmoita Annelille.
    * Kinnusen Leena ilmoittautui jälkikäteen mukaan 
* [Viikon 3 päivitys](https://github.com/KohaSuomi/Koha/discussions/369)
* Githubin esittelyvideot [kaikille](https://youtu.be/cPVSi2xFBIQ) - [pääkäyttäjille](https://youtu.be/J-lzJv7ginE)
* [Kirkesin järjestelmäasetusten läpikäynti, osa 1](https://youtu.be/lyETIF-Xd2Y)
* Tilastoinnissa virhe [KPOKM-5](https://github.com/KohaSuomi/koha-plugin-OKM-stats/issues/5) /Emmi
  * Emmi korjaa virheen ja tiedottaa, kun tilastot on luotu uudelleen.
  * Tätissä on [SQL-kysely](https://tati.koha-suomi.fi/cgi-bin/koha/reports/guided_reports.pl?phase=Run+this+report&reports=243&limit=200), jolla voi hakea tietueet, joissa luokka alkaa kirjaimella. 
* Redmineen kirjautuminen otetaan pois päältä muilta kuin pääkäyttäjiltä.
* [Asiantuntijaryhmän kokous](https://koha-suomi.fi/asiantuntijaryhma2023#asiantuntijaryhm%C3%A4n-muistio-123)
  * [Finna-kehitysehdotukset](https://koha-suomi.fi/asiantuntijaryhma2023#2-finna-kehitysehdotukset)
  * [Infoboksin piilotuksen poisto](https://koha-suomi.fi/dokumentaatio/intranetusercss/#asiakkaan-tietoruudun-piilotus-asiakastiedoista-vasemmasta-reunasta)
    * Tarkista, että HidePersonalPatronDetailOnCirculation asetus on päällä

**Vaara**
* Tuplaverkkomaksuja oli lopulta vain kourallinen, neljä oikeasti tuplasti maksettuja (suuruudeltaan 1,80-5,25 euroa). Toivotaan, että näitä ei tule enempää.
* Joensuun kaupunki ilmoitti perjantaina iltapäivällä, että Ceepos-kassaan kirjautuminen muuttuu (kysyy käyttäjätunnusta). Tieto ei tietenkään kulkeutunut lauantaina työskenteleville, joten kassa pysyi kiinni. Täytyy antaa palautetta muutosten ajankohdan suunnittelusta.

**Lumme**
* Varkaudessa huomattiin OKM tilaston epäonnistuminen vuodelta 2022. Kehittäjät korjaavat tilastot maanantaihin 23.1. mennessä.
* Normaalia ylläpitoa.

**Kyyti**
* CD-levyjen laina-aikaa pidennettiin 28 vuorokauteen viime viikolla.
* Haminan kaupunki on toteuttanut mobiiliapplikaation, jossa on myös sähköinen kirjastokortti sekä tiedonhaku, varaus ja lainojen uusinta. Rajapinta Kohaan on tehty. Löytyy sovelluskaupoista Hamina-haulla.

**OUTI**
* Verkkokirjastossa oli viikonloppuna la-yönä ja su-aamupäivällä jumitilanne, joka aiheutti sen, etteivät asiakkaat saaneet palvelussa näkyville omia lainoja ja varauksia. Ongelman aiheutti arkistointiajon jumiutuminen. Sama ongelma oli myös Vaskissa ja Lapissa.
* Tuplaverkkomaksujen (10 kpl) aiheuttajan selvittäminen vielä vaiheessa.
* Raahen finvoice laskutuksen testaukset ehkä alkamassa lähiaikoina. Oulun laskutuspohjassa vielä vähän säätöä.
* Oulun Byströmin nuorten palvelun kokoelma (alle 1000 nidettä) tulossa käyttöön koko OUTIlle.
* Oulun omatoimikirjastojen laitteistoja vaihdetaan Mikro-Väylän laitteista Lyngsoin laitteisiin.

**Helle**
* Finna-toimisto ilmoittanut yhdestä verkkomaksusta, joka ei ole poistunut Kohasta.
* Niteet/Näytä niteen lainahistoria -tiedosssa ihmetyttänyt Viimeisin havainto -kentän aika, joka on versionvaihtopäiväyksen ajalta: 7.6.2022 12:59. Sama tieto on sekä niteen sijaintikirjastolla (Tesjoki) että kotikirjastolla (Loviisa). Esim. nide itemnumber=1418340, joka on ollut saatavilla versionvaihdon aikaan.
* Onkohan Kohasta toimivaa rajapintaa Konica-Milton-tulostuspalvelulle? Palaverissa saatu tieto: Jos nykyiset Kohan rajapinnat eivät ole yhteensopivia, vaatii rajapinta Koha-kehitystä. Kouvolassa on käytössä Canon-tulostuspalvelu ja Kohan rajapinta toimii.
* Mikä onkaan käytäntö muilla kimpoilla e-palveluihin kirjautumiseen silloin, kun kyseessä on esim. yhteisöasiakas (ei henkilöasiakas)?
* Ehdotettu, että OKM-tilastoinnin kauno/tieto-jaottelu perustuisi niteen luokkaan eikä tietueen luokkaan. Kokouksen jälkeen katsoin, mitä OKM-ohjeistus kertoo:  Kirjat jaetaan aikuisten sekä lasten ja nuorten kauno- ja tietokirjoihin kunkin kirjaston oman käytännön mukaan.
Tieto mainitaan (ainakin) kohdassa 3 Aineistot ja kokoelmat, Kauno ja tietokirjat sekä kohdassa 4 Aineisto: lainaus
https://www.kirjastot.fi/sites/default/files/content/Yleisten_kirjastojen_tilasto-ohjeet_2022_0.pdf

**Lappi**
* Ceepos-kassasta tulee ylimääräisiä maksujen poistoja. Onko vika kassassa vai käyttäjässä? Ongelma vielä selvityksessä. Todennäköisesti käyttäjässä, ohjeistetaan uudelleen.
* Valmistelussa Kysy Kohasta -tilaisuus Lapin henkilökunnalle sekä Kohan käyttäjäryhmän kokous. 

**Vaski**
* Raportteja siivotessa ihmetelty Antin tekemiä raportteja ja mietitty onko ne tehty jostain yhteisestä tarpeesta.
* Versiopäivityksen testikannasta kiinnostaa tuleeko data anonymisoituna.
* Finnan maksuongelmat selvityksessä. Ilmeni, että ongelma johtui maksujen pyöristyksestä.

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-3-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 2 muistio

Aika: 10.1.2023 klo 9.15<br />
Läsnä: Anni Rajala (Vaski), Leena Kinnunen ja Pia Kusmin (Lappi), Heli Auranen, Timo Pesonen (Lumme), Reetta Pihlaja (Siilinjärvi), Päivi Knuutinen, Auli Rantasalo, Irina Halminen (Vaara), Veli-Pekka Marjoniemi (OUTI), Tuomas Kunttu (Kyyti), Anneli Österman ja Kodo Korkalo (Koha-Suomi), Johanna Miettunen (3AMK), Kati Sillgren (Helle)

**Yhteiset**
* [Vkon 2 päivitys](https://github.com/KohaSuomi/Koha/discussions/357)
* Keskiviikon huoltokatko / Kodo
  * Huoltokatkon aikana vaihdetaan viallisia muistikampoja. [Toimintasuunnitelma](https://koha-suomi.fi/kohasuomi2023#tammikuun-huoltokatkon-toimintasuunnitelma) 
* Keskiviikon Kirkes-kimpan järjestelmäasetuskoulutus siirretty puoli tuntia myöhemmäksi ja Jitsiin. Uusi aika ja paikka päivitetty [koulutustiedotteeseen](https://github.com/KohaSuomi/Koha/discussions/320).

**Vaski**
* Vaski-tasoinen kellutuskokeilu aloitettu eilen, kokeilussa kellutetaan vain musiikki cd:itä.
* Havaittu, että tilaussanoman käsittely epäonnistunuu välillä ensimmäisellä yrityksellä (https://github.com/KohaSuomi/Koha/issues/353). Tätä saatu jo selviteltyä ja liittyy ilmeisesti ElasticSearch-ongelmaan.


**Lappi**
* Ylimääräisiä tuplasti veloitettuja maksuja 37 kpl, muutama Finnasta ja enemmän Kemin Ceepokselta. Liittynee tikettiin #351
* Muistutettu varalainausjärjestelmästä, suositeltu KOCT:ia. Yhdellä tunnuksella pääsy ei onnistu. 
* SMS-numeron siirto Finnasta Kohaan toimii, korjattu myös mobiilinumeron kopioituminen mobile-kentästä sms-kenttään
* Kerätään kysymyksiä, ei toimivia ja toimivia juttuja Kohasta käyttäjiltä helmikuun lopun Kysy Kohasta-webinaariin
* Virkailijaoikeuksia tarkistettu, mutta ongelmana  raportit, jotka antavat liikaa tietoa

**Lumme**
* vanhentuneet varaukset eivät poistu - satunnainen mutta toistuva ongelma#356. Tehty tiketti 9.1., Emmi hoitaa asiaa
* Asiakkaalla näkyi Palautusilmoitukset välilehdellä palautusilmoituksia. Väittää palauttaneensa toiminto (https://tiketti.koha-suomi.fi/projects/versionvaihto/wiki/Uusia_ominaisuuksia#Ilmoittaa-palauttaneensa-toiminto). Piilotus Intranetusercss  /*Piilotetaan asiakastietojen sivulla näkyvä 'Palautusilmoitukset' nappula (eng. 'Claims')*/ ul.nav.nav-tabs li a#return-claims-tab { display:none;}

**Siilinjärvi**
* ei mainittavaa

**Vaara**
* Myös Vaarassa tuplasti veloitettuja/kuitattuja maksuja eli asiakkailla plussaldoa.
* Muuten normaalia ylläpitoa.

**OUTI**
* OUTIssa myös tuplasti veloitettuja maksuja, asia selvityksessä.
* Henkilökunnalta kyselyä liittyen ongelmiin kausijulkaisujen vastaanottamisessa tilauskauden päättymisen jälkeen. Ratkaisuna tilauskauden jatkaminen.
* Muuten normaalia ylläpitoa.

**Kyyti**
* Keskusteltiin pitkään maksuista, jotka asiakkaat ovat maksaneet kahteen kertaan Finnassa. Toistaiseksi näitä lienee syytä seurata raporteilla.
* CD-levyjen laina-aika muuttuu. Tehty tiketti #358 nidetyyppimuutokselle.

**Helle**
* Koha-näytön yläreunaan lisätyt omat linkit eivät ole enää päällekkäin pienemmillä näytöillä, kun osa omista linkeistä niputettiin samaan alasvetovalikkoon. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-2-muistio) - [Palaa sivun alkuun](/paakayttajat2023)

## Viikko 1 muistio

Aika: 3.1.2023 klo 9.15<br />
Läsnä: Päivi Knuutinen, Irina Halminen ja Auli Rantasalo (Vaara), Heli Auranen, Katja Valjakka, Timo Pesonen (Lumme), Reetta Pihlaja (Siilinjärvi), Piia Semenoff ja Veli-Pekka Marjoniemi (OUTI), Anni Rajala (Vaski), Leena Kinnunen, Pia Kusmin (Lappi)

**Yhteiset**
* Tikettien label "enhancement" on jaettu "kahtia", jotta erottaa paremmin ne kehitysehdotukset, joiden kehitys on asiantuntijaryhmässä päätetty tehdä yhteisössä oman työn sijaan.
  * local enhancement -> kehitys tehdään itse
  * community enhancement -> kehitysehdotus viedään yhteisön bugzillaan.
    *  työnjakoasia: voisiko alkuperäinen tiketin tekijä tehdä bugi-ilmoituksen myös bugzillaan? Päätös: alkuperäinen tiketin tekijä tekee, muut auttaa tarvittaessa.
* [Varauksen tiedot lokilla](https://tiketti.koha-suomi.fi/projects/koha-suomen-dokumentaatio/wiki/Valmiita_SQL-raportteja#Varauksen-tiedot-lokilla) -raportin kuvaus päivitetty vastaaman nykyversiota.
* [Viikon 1 päivitys](https://github.com/KohaSuomi/Koha/discussions/347)
* Kaikki kimpat käy läpi tammikuun loppuun mennessä Redminessä Palaute-projektissa olevat tiketit ja sulkee valmiit ja sellaiset, jotka eivät ole enää ajankohtaisia. Lopuista katsotaan, mitkä kannattaa siirtää uusiksi tiketeiksi GitHubiin.

**Vaara**
* Kysymys Finnassa tapahtuneista varauksista ja niiden poistumisesta muilta kimpoilta. Ainoastaan Lapissa oli vastaava tapaus viime viikolla. Tutkitaan vielä asiaa.
* Ei muuta mainittavaa, vuoden viimeinen viikko oli rauhallinen.

**Lumme**
* Kirjeitä jumittunut 20 lokakuulta asti, lähetetty 14.12. ja myöhemmin muodostuneet kirjeet.
* Suomenniemen toveriin uudet aukiolot. Hypernovalta ei ole tullut blugaria Lari tekee Lumpeille oman.
* Toenperän kirjastojen erottaminen toisistaan tehty Finnassa, kohassa vielä vähän vaiheessa. Kirjastoauto Jasso jatkaa entisten Toenperän kuntien palvelemista.

**Siilinjärvi**
* Tavoitteena tänä vuonna saada käyttöön verkkomaksaminen. Aloitettu vanhojen laskutus- ja perintämappien perkaaminen ja tietojen siivous Kohasta. Kaikenlaisia maksuja sitä löytyykin!

**OUTI**
* Käyttösääntömuutoksia tehty Kohaan
  * uusintojen määrä laskettu 10 -> 7
  * konsolipelien lainamäärä nostettu 2 -> 4 eli asiakas voi lainata nyt yhteensä 8 peliä, jos lainaa 4 lasten konsolipeliä ja 4 aikuisten. Aiheuttaa henkilökunnassa keskustelua.
* Omatoimikirjastojen erä- ja noutopäivä ylityksiä vähennetty tälle vuodelle. Aiheuttaa henkilökunnassa keskustelua.

**Vaski**
* Ei erityisiä kuulumisia. Asiakaspalvelusta tiedusteltu, poistetaanko vanhentuneet maksamattomat automaattisesti. Siivousajoa ei vielä ole käytössä ja se edellyttää huolellista suunnittelua, Anneli vie asian eteenpäin kehittäjien viikkopalaveriin.

**Lappi**
* Rauhallinen vuodenvaihde.
* Käyttäjäoikeuksista on ollut kaksi raporttia, toisella voi hakea kaikkien käyttäjien kaikki oikeudet ja toisella oikeusryhmittäin. Rapsat menneet ilmeisesti rikki edellisessä päivityksessä. Vaaralla ilmeisesti näistä toimiva versio? Lari lupasi katsoa Lapin raportteja. 
* Työn alla käyttäjätunnusten tarkistus, aloitetaan vanhentuneiden maksujen poisto. 

[Palaa muistion alkuun](https://koha-suomi.fi/paakayttajat2023#viikko-1-muistio) - [Palaa sivun alkuun](/paakayttajat2023)
