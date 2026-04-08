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

## Viikko 15
Aika: Ma 13.4.2026<br />
Läsnä:

* Viikon 15 päivitys
* Vastuuttomat tiketit
  * [kaikki tiketit](https://github.com/issues?q=is%3Aopen+is%3Aissue+owner%3AKohaSuomi+archived%3Afalse+sort%3Aupdated-desc+no%3Aassignee+-repo%3AKohaSuomi%2FBugiton+-repo%3AKohaSuomi%2FFinna-kehitysehdotukset)

Viikolla 14 tehty:

## Viikko 14

Maanantain viikkopalaveria ei pidetty pääsiäisen vuoksi. Vastuuttomat tiketit vastuutetaan ensi viikon palaverissa.

* Kodo
  * [Ajastetut ajot testeillä](https://github.com/KohaSuomi/Koha/issues/2236)
    > testicronjobien perussetti listattu (OUTI-test), `update-holds-to-pull`-kuormariski huomioitu, syspref-ohjaus (**RunTestCronjobs**) toteutettu testiajojen määräaikaiseen päälle/pois-kytkentään.
  * [Lappi: Omatoimikirjaston käyttökiellon asettaminen asiakkaalle](https://github.com/KohaSuomi/Koha/issues/2239)
    > estot asetettu.

  * [Lappi: Listaus sip-palvelimelle yhteyden saavista automaateista](https://github.com/KohaSuomi/Koha/issues/2234)
    > kesken; SIP-palvelimelle väärällä RO-tunnuksella yhteyttä ottavat Lapin automaatit; pyydetty SIP-palvelimelta lista yhteyttä ottavista automaateista rajauksen tekemiseksi.
    > Seuraava: SIP-lista ulos ja tunnusten/salasanojen tarkistus niille automaateille, jotka ottavat yhteyttä väärällä RO-tunnuksella.
  * [Vaara: Ceepos kassajärjestelmän muutostyöt](https://github.com/KohaSuomi/Koha/issues/2235)
    > kesken; vanha IPsec-tunneli purettu, uusi liikennöinti kesken; Koha-päähän tarvitaan ceepos-yhteysosoitteen muutos + tarkistuspalaveri + testaus, eteneminen Meita/CPU:n aikataululla.
    > Seuraava: ceepos-yhteysosoitteen muutos Kohaan + yhteistestaus Meita/CPU:n kanssa (palaveri + testit).

  * [/var/etc/hakemiston siivous](https://github.com/KohaSuomi/Koha-25x/issues/169)
    > `/var/etc` siivottu; vanhat tiedostot siirretty `/var/etc/koha/old`-hakemistoon; jatkotoimet tunnistettu (sms_send + koha-conf → utility #105–#108); tiketti avattu takaisin kunnes liittyvät tiketit hoidettu.
    > Seuraava: utility-tikettien #105–#108 läpivienti ja tämän sulkeminen niiden jälkeen.

  * [zebradb-konfigeissa roikkuu viittauksia jaettuun /home/koha/koha-dev:iin](https://github.com/KohaSuomi/koha-suomi-utility/issues/108)
    > viittaukset siivottu, konffit vaihdettu prod- ja test-roolien kontteihin.
  * [Vanhat easticsearch-dumpit ja -hakemistot pois](https://github.com/KohaSuomi/koha-suomi-utility/issues/101)
    > indeksien dumppaus ja synkkaus siirretty versiopäivityksessä Elmalle; vanhat dumpit ja `elasticsearch.ondisk`-hakemistot poistettu / poistettavana tuotannoista ja varmistuksista. (tausta: [Elma tuotantoon](https://github.com/KohaSuomi/koha-suomi-utility/issues/30))
  * [sms_send driverin siirto /var/koha/etc:stä tarkoituksenmukaisempaan paikkaan](https://github.com/KohaSuomi/koha-suomi-utility/issues/105)
    > sms_send todettu YAML-konffiksi (ei driveriä) → jätetty etc:iin.
  * [/home/koha hakemistossa perl5 modulihakemisto](https://github.com/KohaSuomi/koha-suomi-utility/issues/109)
    > korjaus tehty testeillä; `koha_perl_deps.pl` OK; OAI testaus vielä tekemättä.
  * [MariaDB systemd service unitin korjaus](https://github.com/KohaSuomi/koha-suomi-utility/issues/70)
    > todettu, ettei palvelu käynnisty aina automaattisesti.

  * [Vanhat tietokantadumpit pois](https://github.com/KohaSuomi/koha-suomi-utility/issues/104)
    > kesken; tiered dumppeihin siirtymisen jälkeen vanhat tietokantadumpit poistettava varmistusjärjestelmästä manuaalisesti; poistossa huomioitava säilytysajat (erityisesti LTS).
    > Seuraava: poistojen ajosuunnitelma (mitä poistetaan/mistä) + toteutus säilytysaikojen puitteissa + kuittaus tikettiin.
  * [next-roolin konttipohja pitää uusia](https://github.com/KohaSuomi/koha-suomi-utility/issues/110)
    > kesken; next-roolin konttipohja päivitettävä vastaamaan maaliskuu 2026 -versionvaihdon jälkeisiä tuotantoja ennen seuraavaa versiopäivitystä.
    > Seuraava: erot tuotanto ↔ next -konttipohja kartoitetaan ja konttipohja päivitetään vastaamaan nykyisiä tuotantoja.
  * [LimitRequestBody-asetuksen muuttaminen palvelimella](https://github.com/KohaSuomi/koha-suomi-utility/issues/69)
    > kesken; Apachen `LimitRequestBody` ei rajoittava (apache “unlimited”); rajoite HAProxy/palomuurissa. HAProxyyn suunnitellut `tune.bufsize`/`tune.maxrewrite`-muutokset päätetty jättää tekemättä, koska ongelma muuttui Koha 3/2026 -versiossa ja epäonnistuu myös pienillä määrillä (vika ei todennäköisesti HAProxyssä).
    > Seuraava: toisto pienellä aineistolla + lokien keruu (Koha + LB/HAProxy) ja rajaus, onko kyse request-koosta vai sovellus-/backend-ongelmasta.


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
  * Tein palautekyselyn pääkäyttäjille versionvaihdon sujumisesta. Mikä meni hyvin/huonosti, mitä voisi parantaa jne.
  * Lumpeissa löytyi vielä neljä yli 20 merkkistä viivakoodia, jotka aiheuttivat Perustiedot-näytöllä virheilmoituksen. Nämä ohjeistettiin korjaamaan käsin.
  * Vaarassa käyttäjällä ei näkynyt Perustiedot-näytöllä Tuo/Vie-nappi, ongelma korjaantui selaimen välimuistin tyhjennyksellä.
  * TäTissä huomasin sellaisen ongelman, että jos IntranetUserJS: Generate PIN codes -liitännäinen on aktivoitu, mutta sinne ei ole määritetty mitään asiakastyyppejä, niin kaikille generoituu nelinumeroinen pin-koodi. Kävin epäaktivoimassa liitännäisen, koska sitä ei TäTissä tarvita.
  * Suljin signum-muutokseen liittyviä tikettejä ja jätin auki lähinnä OUTIn muutokseen liittyvät. Ne tehdään sitten, kun OUTIssa on saatu vietyä päätökseen projektia varten tarvittavat muutokset.
  * Kyytissä ja OUTIssa on tullut käyttäjiltä ilmoituksia, että he ovat saaneet Virhe 500 -ilmoituksen, kun ovat lainanneet toiselle asiakkaalle jo lainassa olevia niteitä ja valinneet valinnan "Muista istunnolle", että lainaesto ohitetaan. Testasimme tätä Pirkko-Liisan kanssa sekä testeillä että tuotannossa superlibraian-oikeuksilla, perusvirkailijaoikeuksilla sekä minimioikeuksisilla tunnuksilla emmekä saaneet toistettua virheilmoitusta. Ehdotin ongelman johtuvan välimuistiongelmasta ja että käyttäjät voisivat tyhjentää selaimen välimuistinsa ja yrittää uudelleen. [Tiketti Koha-25x #254](https://github.com/KohaSuomi/Koha-25x/issues/254)
* Johanna
  * [Virhekäsittelyt eivät toimi oikein](https://github.com/KohaSuomi/koha-plugin-visual-label-tool/issues/11)  
    > Käännösten lisääminen Tarratulostus-liitännäiseen rikkoi muokkauksessa virheviestien näkymisen. Samalla parantelin virheviestejä, jotta niistä ymmärtäisi paremmin mikä on vikana.
  * [Tulosta ilmoituksia -liitännäisessä peruuta-painiketta painaessa sivu ei päivity automaattisesti](https://github.com/KohaSuomi/Koha/issues/2221) 
    > Tähän viety korjaus testeille, vaatii vielä parantelua.
  * [Lappi: Testikantaan päälle kaukolainamoduuli](https://github.com/KohaSuomi/Koha/issues/2216)
    > Lisätty testeille.
  * [Lappi: Suomi.fi -viestien käyttöönotto](https://github.com/KohaSuomi/Koha/issues/2214)
      > Vastuutettu: johannaraisa
  * [Noutohyllyjen tuonti nextiltä testille](https://github.com/KohaSuomi/Koha-25x/issues/252) ja OUTI:lle tyhjennetty noutohyllytaulut.
  * [OAI-setin siivousskripti](https://github.com/KohaSuomi/koha-plugin-broadcast-biblios/issues/19)
      > Siivous on tehty Tätissä, ja varmistettu ettei uusia enää synny.
  * [Käyttöoikeuksia voi asettaa vain tietyille asiakastyypeille](https://github.com/KohaSuomi/Koha/issues/2237)
      > Tiketti avattu
  * [Vaski: Kulttuurikorttiasiakkaiden haku Raportterin kautta epäonnistunut](https://github.com/KohaSuomi/Koha/issues/2232)
      > Vastuutettu: johannaraisa.
      > Paranneltu muuttujien ja virheiden käsittelyä. Testattu testeillä ja viety testauksen jälkeen tuotantoon, jotta näkee mikä voisi kyselyn rikkoa.
* Emmi
  * Kirkesiin ajettu cn_sort-kenttien korjaus [Kirkes: tietokannassa virheellisiä cn_sort-kenttiä](https://github.com/KohaSuomi/Koha/issues/2024)
  * Testeille tehty muutoksia indeksointijonon kokoon ja muutos dokumentoitu
  * Laskutustyökaluun lisätty testi-vipu, jolla voi generoida testilaskuja palvelimelle. Laskut generoituvat erilliseen test-hakemistoon ja ne merkitään tietokantaan failed-tilaan. Lisäksi niille tule oma failure_code:nsa. [Laskutusliitännäinen: Test-vipu run_finvoices.pl ajoon](https://github.com/KohaSuomi/koha-plugin-overdue-tool/issues/35)
  * Varaustyökaluun ei pysty tällä hetkellä viemään raportilla kuin alle 50 varausta. Ongelma näyttäisi poistuneen yhteisön versiossa 25.05.05, mutta korjaavaa committia ei ole vielä löytynyt. [Varausten vienti raportilta erämuokkaukseen epäonnistuu isoilla määrillä](https://github.com/KohaSuomi/Koha/issues/1980)

* Lari

  **Tiketit (kommenttini)**

- *KohaSuomi/Koha-25x#192* – 99-sanomien käsittely SIP-palvelimen ohi
  - Tiketti: https://github.com/KohaSuomi/Koha-25x/issues/192
  - Kommentti: https://github.com/KohaSuomi/Koha-25x/issues/192#issuecomment-4126292134 (2026-03-25T12:41:26Z)
      Bibliothecan automaatit eivät toimi uuden toiminnallisuuden kanssa. Ongelma on ilmeisesti checksummien tai sequence numberien kanssa. Automaatit lähettävät toteutuksen kanssa viestin uudelleenvälittämispyyntöä (97):
      
      Request ACS Resend
      This message requests the ACS to re-transmit its last message. It is sent by the SC to the ACS when the
      checksum in a received message does not match the value calculated by the SC. The ACS should
      respond by re-transmitting its last message, This message should never include a “sequence number”
      field, even when error detection is enabled, (see “Checksums and Sequence Numbers” below) but would
      include a “checksum” field since checksums are in use.
      97
      
      [2026-03-25 14:10:48,646] INFO  ---> 97AZFEF5
      [2026-03-25 14:10:48,646] INFO  <--- 941AY0AZFDFD
      [2026-03-25 14:10:54,662] INFO  ---> 97AZFEF5
      [2026-03-25 14:10:54,663] INFO  <--- 941AY0AZFDFD
      
      
      
  - Kommentti: https://github.com/KohaSuomi/Koha-25x/issues/192#issuecomment-4126304055 (2026-03-25T12:43:04Z)
      Toiminnallisuus on poistettu tuotannoista ja sanomat käsitellään sip-palvelimella. Tätä toteutusta ja sen korjausta pitäisi pystyä jotenkin testaamaan Bibliothecan automaatin kanssa.


- **KohaSuomi/Koha#2208** – OUTI: Maksu ei siirtynyt Ceeposiin ja Koha antoi virheilmoituksen "Missing from configuration"
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2208

  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2208#issuecomment-4161967280 (2026-03-31T11:32:10Z)
      Toimimaton nappi on piilotettu Lainausnäkymästä. Testattavana testeillä.

- **KohaSuomi/Koha#2210** – Hyllyvarausraportille näppäintoiminto pudotusvalikkoihin
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2210
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2210#issuecomment-4143125802 (2026-03-27T14:43:42Z)
      Tähän löytyi selitys "zero-width space" merkinnöistä datassa joka päätyi taulukkoon, eivätkä kirjaimet/näppäimet siksi täsmänneet toisiaan pudotusvalikkovaihtoehtojen kanssa. Korjaus viety testeille.
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2210#issuecomment-4153737961 (2026-03-30T09:55:09Z)
      Poistin holds-to-pull-skriptistä "zero-width space"-lisäykset jotta näppäinkomennot tarttuvat suodatusarvoihin ja tein mm. Hyllyssä- ja Noutopaikassa-sarakkeille kustomoidut filtterit. Testatkaa muutkin sarakkeet, että toimivat edelleen täsmällisellä valinnalla. Testattavana testeillä.
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2210#issuecomment-4154339925 (2026-03-30T11:32:53Z)
      Lisäsin saman kustomoidun filtteröinnin käyttöön näille muillekin sarakkeille, millä on pudotusvalikko ja missä voi olla useampi arvo valittavana. Testattavana testeillä.

- **KohaSuomi/Koha#2223** – Yksityisoikeudellisten maksujen poistoajo ei päällä?
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2223
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2223#issuecomment-4152668945 (2026-03-30T06:47:14Z)
      Nämä ajot ovat olleet poikki kaikissa kimpoissa versionvaihdosta lähtien johtuen siitä, että ajastetun ajon $NEWTRIG-skripti puuttuu tuotannoista, eikä ajot siksi ole menneet läpi.
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2223#issuecomment-4153951879 (2026-03-30T10:30:51Z)
      Nyt kaikkin tuotantoihin on korjattu ajastettu ajo. Ajautuu siis ensi yöstä taas päivittäin ja missatut maksutkin tulevat käsiteltyä.

- **KohaSuomi/Koha#2190** – Varauksen noutomuistutusilmoituksille sallittavat viestienvälitystavat
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2190
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2190#issuecomment-4160773143 (2026-03-31T08:16:49Z)
      Sovittiin kehittäjäpalsussa että siivotaan ei-halutut viestivalinnat pois asiakkailta tietokannasta ennemmin kuin muutetaan skriptin toimintaa (vipu tiettyjen toimitustapojen pakottamiseksi), jotta skripti toimii käyttöliittymässä näkyvien(/piilotettujen) valintojen mukaisesti. Ei maksa mittee.

- **KohaSuomi/Koha#2233** – Maksujen muodostus hidasta versionvaihdon jälkeen
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2233
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2233#issuecomment-4168175381 (2026-04-01T07:40:48Z)
      Tutkimusteni mukaan accountlines-tauluun on tullut versionvaihdossa uusi sarake old_issue_id ja issues/old_issues-tauluun checkin_library joilla voi olla merkitystä. Reserves-taulussa uutena deleted_biblionumber.

- **KohaSuomi/Koha#2198** – Vaskille käyttöön versiopäivityksen yhteydessä varauksen noutomuistutuksen muutokset
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2198
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2198#issuecomment-4169222458 (2026-04-01T10:53:43Z)
      Kolmella asiakkaalla on muu kuin NULL tai 1, heillä on 0 days_in_advance-arvona (432421,121798, 127230), saako ylikirjoittaa?
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2198#issuecomment-4169354657 (2026-04-01T11:19:45Z)
      Ajettu:
      
      MariaDB [vaskiprod]>   UPDATE borrower_message_preferences bmp
          -> SET days_in_advance = 1
          -> WHERE bmp.message_attribute_id = 10
          ->   AND EXISTS (
          ->       SELECT 1
          ->       FROM borrower_message_transport_preferences bmtp
          ->       WHERE bmtp.borrower_message_preference_id = bmp.borrower_message_preference_id
          ->         AND bmtp.message_transport_type = 'email'
          ->         AND bmp.days_in_advance IS NULL
          ->   );
      
      Query OK, 104000 rows affected (4.459 sec)
      Rows matched: 104000  Changed: 104000  Warnings: 0
      

- **KohaSuomi/Koha#2227** – Helle, asiakkaalle muodostunut Varauksen noutomuistutus voimassa olevasta lähiaikoina vanhenevasta varauksesta
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2227
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2227#issuecomment-4169532227 (2026-04-01T11:50:44Z)
      Lisäsin testeille noutomuistutusten luontiskriptiin ehdon, että vain varaukset, joiden tila on W"odottaa" käsitellään.
      https://github.com/KohaSuomi/Koha-25x/commit/bb3d199fc06dfeb9aa293498546327d525c198e2
      
      Muutos viety testeille.

- **KohaSuomi/Koha#1847** – Self service-pluginin repositorion korvaaminen Koha-Suomen versiolla.
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/1847
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/1847#issuecomment-4175978538 (2026-04-02T09:40:00Z)
      Plugin on poistettu käytöstä.

- **KohaSuomi/Koha#2079** – SIP2-autentikointi lokittuu virheellisesti verkkokirjastossa tapahtuvaksi
  - Tiketti: https://github.com/KohaSuomi/Koha/issues/2079
  - Kommentti: https://github.com/KohaSuomi/Koha/issues/2079#issuecomment-4176213764 (2026-04-02T10:24:36Z)
      Muutos on tuotannoissa.

  **Kommitit**

- **KohaSuomi/Koha-25x**
  - `6276f0d` 2026-03-30T09:38:40Z – KOHA-2210 Use custom filter plugin in template for filter typing and exact matches
    https://github.com/KohaSuomi/Koha-25x/commit/6276f0d34abdb7794a2d9a3d09a21d63600b4468
  - `8c28b94` 2026-03-30T11:22:50Z – KOHA-2210 Use custom list filter for all dropdown columns
    https://github.com/KohaSuomi/Koha-25x/commit/8c28b94ab8b883ba97f2b4c7c0050778cc9c19e7
  - `bb3d199` 2026-03-31T07:40:23Z – Only deal with reserves with waiting status
    https://github.com/KohaSuomi/Koha-25x/commit/bb3d199fc06dfeb9aa293498546327d525c198e2

- **KohaSuomi/koha-plugin-ceepos-integration**
  - `fa7053e` 2026-03-31T11:08:25Z – KOHA-2208 hide paycollect button in circulation.pl that doesn't work with Ceepos
    https://github.com/KohaSuomi/koha-plugin-ceepos-integration/commit/fa7053ef54730468ec18f0e17738a2cff95c8dc3

* Kodo
  * Koha versiopäivityksen yliheitto + ajot
    > yliheitto ja ajot ajettu sunnuntain 2026-03-22 – maanantain 2026-03-23 välisenä yönä.
  * [FacetSortingLocale-järjestelmäasetuksesta puuttuu kielivaihtoehdot](https://github.com/KohaSuomi/Koha-25x/issues/246)
    > tilanne kuvattu: ongelma ei ilmene testeillä; TäTi ja Siili ok; muissa kimpoissa kielivaihtoehdot näkyvät/puuttuvat vaihtelevasti. Kokeellinen korjaus tehty, mutta tulos laiha.
  * [Lainaus ja palautus -sivujen sivuvalikossa väärä linkki](https://github.com/KohaSuomi/Koha-25x/issues/249)
    > linkki korjattu kiireellisenä tuotantoihin; pysyvämpi korjaus tehty ja tulossa buildissa tuotantoon; tiketti jätetty auki odottamaan tuotantoon päätymistä.
    > Seuraava: varmistus viikkopäivityksen jälkeen, että pysyvä korjaus on tuotannossa, ja tiketin sulku.
  * [EDItX-plugin - koha-plugin-editx](https://github.com/KohaSuomi/Koha-25x/issues/83)
    > hankinta tuotti `HANK_`-alkuisia viivakoodeja kimpoissa joissa halutaan automaattigeneroitu viivakoodi, korjaus tehty EDItX-pluginille ja testattu toimivaksi.
    > commitoitu ja pushattu, ei vaadi muita toimenpiteitä, seuranta mahdollisten uusien havaintojen varalta
  * [Vanhentuneiden varausten peruuttaminen (crontab)](https://github.com/KohaSuomi/Koha-25x/issues/204)
    > tilanne todettu tarkistettavaksi ensi viikolla, vanha cronjob deprekoitu ja turha, mutta ei toiminnallista haittaa.
    > Seuraava: crontab-rivien läpikäynti kimpoittain ja päätös vanhan rivin poistosta / uuden rivin varmistus.
  * [99-sanomien käsittely SIP-palvelimen ohi](https://github.com/KohaSuomi/Koha-25x/issues/192)
    > Bibliothecan automaattien yhteensopivuusongelma (97 resend / checksum/sequence -epäily, mahdollinen rivinvaihto/carriage return -ero)
    > Korjauksen testauksesta sovittu Bibliothecan kanssa.
    > Seuraava: testaus Bibliothecan automaatilla, jotta korjaus voidaan validoida ennen uudelleenkäyttöönottoa.
  * Runsaasti erilaisia SIP-tunnusongelmia monissa kimpoissa.
    > Tunnuksia putoillut kyydistä versiopäivityksessä, korjailtu sitä mukaa kun tulee vastaan.
    > Seuraava: tarkistettava kaikkien kimppojen sip-konfiguraatioiden oikeellisuus
  
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
