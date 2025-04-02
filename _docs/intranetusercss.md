---
title: 'IntranetUserCSS'
permalink: /dokumentaatio/intranetusercss/
redirect_from:
  - /theme-setup/
toc: true
---

IntranetUserCSS-järjestelmäasetuksella pystyy "ohittamaan" Kohan CSS-määritykset ja esimerkiksi piilottamaan eri sivuilta elementtejä tai säätämään fontin kokoa ja väriä. Tämä on kevyempi tapa säätää näkymiä koskematta Kohan sivupohjiin.

Jokaisen kohdalle on merkitty, missä Koha-versiossa se toimii.


## Asiakkaat

### Piilota Asiakkaat-sivulla hausta osoite-hakuvaihtoehto

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Asiakkaat-sivulla hausta osoite-hakuvaihtoehto */
body#pat_member.pat .searchfieldstype option[value='full_address'] { display:none; }
body#pat_member.pat .searchfieldstype_filter option[value='full_address'] { display:none; }
```

### Piilota asiakkaan kuva, jos asiakkaalla ei ole sellaista

Versio: 17.05

```
/* Piilota asiakkaan kuva, jos asiakkaalla ei ole sellaista */
li#patronbasics img[src$="blank.png"] { display: none !important; }
li.email { background: none !important; }
```

### "Kirjoitussuojaa" sotu-avain-kenttä

Sotu-avain-kentän voi "kirjoitussuojata" niin, että siihen pystyy Lisää sotu -toiminnolla lisäämään sotu-avaimen, mutta käyttäjä ei pysty muokkaamaan kentässä olevaa tietoa. Käyttäjä pystyy poistamaan tiedon kentän vieressä olevalla "Tyhjennä"-linkillä.

Huomioi, että patron_attr_4-osiossa oleva numero riippuu siitä, kuinka monentena sotu-avain on näytöllä. Esim. OUTI-kirjastoissa numerona on 3 ja Hellessä 4. Voit tarkistaa numeron klikkaamalla asiakkaan muokkausnäytöllä hiiren oikealla sotu-avain-kenttää ja valitsemalla "Inspect Element (Q)" (toimii ainakin Firefoxilla).

Tarpeellisuus: Ei tarpeen versiosta 24.05 lähtien<br />
Versio: 23.11

```
body#pat_memberentrygen.pat textarea#patron_attr_4 { pointer-events: none; }
```

### Käyttäjätunnus-osion piilottaminen asiakkaan muokkausnäytöltä

Käyttäjätunnus-osion piilottaminen asiakkaan muokkausnäytöltä.

Versio: 17.05

```
/* Piilota Käyttäjätunnus-osio asiakkaan muokkausnäytöltä */
#pat_memberentrygen.pat fieldset#memberentry_userid { display:none; }
```

### Asiakasmääreen piilottaminen tiedot-näytöltä

Versio: 17.05

```
/* Piilota asiakasmääre tiedot-näytöltä */
div#patron-extended-attributes ol li:nth-child(1) { display:none; }
```

### Piilota asiakkaan ikä Tiedot-välilehdellä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakkaan ikä tiedot-näytöllä */
body#pat_moremember.pat span.age_years { display: none; }
```

### Piilota Näytä aina lainat reaaliaikaisesti -valinta

Tarpeellisuus: Suositeltava, parantaa suorituskykyä.<br />
Versio 24.05

```
/* Piilota Näytä aina lainat reaaliaikaisesti / Always show checkouts immediately -täppä. Piilottaa sekä lainaus- että tiedot-näytöltä. */
body#circ_circulation.circ input#issues-table-load-immediately { display: none; }
body#circ_circulation.circ label[for="issues-table-load-immediately"] { display: none; }
body#pat_moremember.pat input#issues-table-load-immediately { display: none; }
body#pat_moremember.pat label[for="issues-table-load-immediately"] { display: none; }
```

### Säädä Viesti asiakkaalle -viestin väriä

Tarpeellisuus: Vapaaehtoinen<br />
Versio 24.05

```
/* Säädä Viesti asiakkaalle -viestin väriä */
#messages.circmessage span { color:#009900; font-weight: bold;}
#messages.circmessage span.circ-hlt { color:#cc0000; }
```

### Piilota Tiedot-sivulla Alternative contact / Vaihtoehtoinen yhteys -osio

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Tiedot-sivulla Alternative contact / Vaihtoehtoinen yhteys -osio */ 
#patron-alternative-contact,
#patron-alternative-contact + div { display:none; }
```

### Piilota asiakkaan tiedot -sivulta Alternate address/ Vaihtoehtoinen osoite -osio

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakkaan tiedot -sivulta Alternate address/ Vaihtoehtoinen osoite -osio */
#patron-alternate-address,
#patron-alternate-address + div { display:none; }
```


### Piilota asiakkaan muokkauksessa Yhteystiedot-boksista Näkyy kuljetuskuitissa -vihjeet näkyvistä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakkaan muokkauksessa Yhteystiedot-boksista Näkyy kuljetuskuitissa -vihjeet näkyvistä */ 
fieldset#memberentry_contact.rows div.hint { display: none; }
```

### Piilota maksujen mitätöintitäppä Asiakkaan tiedot- ja Lainaus-sivuilta

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Asiakkaan tiedot -sivulla lainat-taulu */
/* Piilota Poista myöhästymismaksut palautettaessa -täppä */
#pat_moremember #issues-table label[for="exemptfine"] { display:none; }
#pat_moremember #issues-table input#exemptfine { display:none; }

/* Lainaus-sivulla Asiakkaan lainat-taulu */
/* Piilota Poista myöhästymismaksut palautettaessa -täppä */
#circ_circulation #issues-table label[for="exemptfine"] { display:none; }
#circ_circulation #issues-table input#exemptfine { display:none; }
```

### Piilota asiakkaan tiedot -näytöltä muokkaa-napit

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota asiakkaan tiedot -näytöltä muokkaa-napit. Jatkossa muokkaus onnistuu vain yläreunan Muokkaa-napista */
body#pat_moremember a[href*="&step="] { display: none; }
```

### Piilota Lainaus-sivulla Muokkaa-nappi Kortti kadonnut -ilmoituksen perästä

Liittyy [tikettiin #128](https://github.com/KohaSuomi/Koha-24.05/issues/128).

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota asiakkaan Lainaus-sivulla Muokkaa-nappi Kortti kadonnut -ilmoituksen perästä, koska tietoja ei voi sitä kautta tallentaa sotu-avaimen tarkistuksen vuoksi */
body#circ_circulation.circ a[href*="&step="] { display: none; }
```

### Piilota Ei asiakas -takaaja -kohta asiakkaan muokkauksesta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Ei asiakas -takaaja -kohta asiakkaan muokkauksesta */
body#pat_memberentrygen.pat fieldset#non_patron_guarantor.rows { display:none; }
```

### Piilota Bookings/Ennakkovaraukset -välilehti lainauksessa/tiedot-sivulla

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Bookings/Ennakkovaraukset -välilehti lainauksessa/tiedot-sivulla */
 a#bookings-tab { display: none; }
```

### Piilota Tarkasta edelliset lainat -kohta asiakkaan muokkauksesta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Tarkasta edelliset lainat -kohta asiakkaan muokkauksesta */
body#pat_memberentrygen.pat label[for="checkprevcheckout"] { display:none; }
body#pat_memberentrygen.pat select#checkprevcheckout { display:none; }
```

### Piilota Tarkasta edelliset lainat -kohta asiakkaan tiedot-sivulla

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakkaan tiedot -sivulta "Tarkasta edelliset lainat" -kohta */
body#pat_moremember.pat li#patron-checkprev { display:none; }
```

### Piilota ennakkoilmoituksen valinnasta 0 päivän keston

Jos ennakkoilmoitukseen valitsee päiväksi 0, viesti ei lähde ollenkaan.

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota ennakkoilmoituksen valinnasta 0 päivän keston. Käy lisäksi valitsemassa asiakastyyppien ylläpidossa asiakastyyppien viestiasetuksiin jotain muuta kuin 0 oletukseksi. Valinta tehtävä kaikille asiakastyypeille erikseen. */
body#pat_memberentrygen.pat fieldset#memberentry_messaging_prefs.rows option[value='0'] { display:none; }
```
### Piilota asiakkaan viestiasetuksista ennakkoilmoituksen viive -vaihtoehdoista 0 ja 8-30

Tarpeellisuus: Vapaaehtoinen tai vaihtoehtoinen tätä edeltävälle<br />
Versio: 24.05

```
/* Asiakkaan viestiasetukset, ennakkoilmoituksen viive-vaihtoehdoista arvot 0 ja 8-30 piiloon */
body#pat_memberentrygen.pat [name="2-DAYS"] :is([value='0'], [value='8'], [value='9'], [value='10'],
 [value='11'], [value='12'], [value='13'], [value='14'], [value='15'], [value='16'], [value='17'], [value='18'], [value='19'], [value='20'],
 [value='21'], [value='22'], [value='23'], [value='24'], [value='25'], [value='26'], [value='27'], [value='28'], [value='29'], [value='30']) { display:none; }
```

### Piilota käyttäjätilin huomautukset asiakaslomakkeelta (Tarkista osoite)

Tarpeellisuus: Ei tarpeen versiosta 24.05 lähtien, korvattu piilottamalla tieto BorrowerUnwanted-järjestelmäasetuksen avulla<br />
Versio: 23.11

Osoitteen tarkistustarve ei saa aiheuttaa lainakieltoa.

Suositeltava, koska näiden perusteella ei saa tulla lainakieltoa lain mukaan.
```
/* Piilota Käyttäjätilin huomautukset asiakaslomakkeelta (Tarkista osoite) */ 
#pat_memberentrygen #memberentry_account_flags { display:none; }
```

### Piilota noutomuistutus asiakaslomakkeelta ja viestiasetuksista

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Noutomuistutuksen piilotus asiakaslomakkeelta */
body#pat_memberentrygen #memberentry_messaging_prefs table tbody tr:last-child { display:none; }

/* Noutomuistutuksen piilotus tiedot-sivulta */
body#pat_moremember #patron-messaging-prefs table tbody tr:last-child { display:none; }
```

### Piilota Kooste-sarake asiakkaan viestiasetuksista

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

Liittyy [tikettiin 126](https://github.com/KohaSuomi/Koha-23x/issues/126). Jos on käytössä muita sarakkeita (esim. suomi.fi), niin muuta sulkeissa olevaa lukua sen mukaan. Tämä piilottaa 5. sarakkeen.

```
/* Piilota kooste-sarake Kohan viestiasetustaulusta */
fieldset#memberentry_messaging_prefs th:nth-child(5),
fieldset#memberentry_messaging_prefs td:nth-child(5),
div#patron-messaging-prefs th:nth-child(5),
div#patron-messaging-prefs td:nth-child(5) {
  display:none;
}
```


### Piilota Salli automaattinen uusinta -kohta

Asiakkaan lisäys/muokkausnäytöllä on kohta "Salli automaattinen uusinta", vaikka toiminto ei olisi sallittu laina- ja maksusäännöissä. Kohdan saa piiloon seuraavasti. Päivitys 8.4.2024: Tätä piilotusta ei enää tarvita, vaan tiedon saa piiloon BorrowerUnwantedField-järjestelmäasetukella valitsemalla autorenew_checkouts-kohdan.

Tarpeellisuus: Ei tarpeellinen<br />
Versio: 22.11

```
/* Automatic renewal / Automaattinen uusinta -checkboxi piiloon */
body#circ_circulation #set-automatic-renewal { display: none; }
```

### Asiakkaan tietoruudun piilotus asiakastiedoista vasemmasta reunasta

Tarpeellisuus: Ei tarpeen<br />
Versio: 21.11<br />
Asiantuntijaryhmä on päättänyt, että tietoruutu on näkyvillä, jotta tilin lukkiutuminen näkyy virkailijalle.

```
/* Asiakkaan tietoruudun piilotus vasemmasta reunasta */
div.patroninfo { display: none; }
```

### Piilota asiakastietojen tulosta-valikosta Asiakastietojen yhteenveto

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakastietojen tulosta-valikosta Asiakastietojen yhteenveto */ 
body#pat_moremember.pat ul.dropdown-menu li:nth-child(1) a.printslip {display: none}
body#circ_circulation.circ ul.dropdown-menu li:nth-child(1) a.printslip { display: none; }
body#pat_pay.pat ul.dropdown-menu li:nth-child(1) a.printslip { display: none; }
body#pat_notices.pat ul.dropdown-menu li:nth-child(1) a.printslip { display: none; }
body#pat_statistics.pat ul.dropdown-menu li:nth-child(1) a.printslip { display: none; }
```

### Piilota asiakastietojen tulosta-valikosta Tulosta erääntyneet -valinnat

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakastietojen tulosta-valikosta Tulosta erääntyneet */ 
body#pat_moremember.pat ul.dropdown-menu li:nth-child(4) a#print_overdues { display: none; }
body#circ_circulation.circ ul.dropdown-menu li:nth-child(4) a#print_overdues { display: none; }
```

### Piilota Näytä takaajalle lainat ja Näytä takaajalle maksut -kohdat Tiedot-näytöltä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Näytä takaajalle lainat ja Näytä takaajalle maksut -tiedot asiakkaan Tiedot-sivulta */
#patron-privacyguarantor + li { display: none; }
#patron-privacyguarantor { display: none; }
```

### Säädä Lisää viesti -popparin alasvetovalikon leveyttä

Tarpeellisuus: Ei enää tarpeellinen versiosta 24.05 lähtien<br />
Versio: 23.11

Säätö tehdään sekä lainaus- että tiedot-sivulle.

```
/* Säädä Lisää viesti -popupissa valikon leveys kapeammaksi lainaus- ja tiedot-näytöillä */
body#pat_moremember.pat.modal-open select#select_patron_messages { width: 556px; }
body#circ_circulation.circ.modal-open select#select_patron_messages { width: 556px; }
```

### Piilota kirjautumistunnusosio asiakaslomakkeelta

Tarpeellisuus: Ei tarpeen versiosta 24.05, jos userid ja password -kentät on piilotettu BorrowerUnwantedFields-asetuksella<br />
Versio: 24.05

```
/* Piilota kirjautumistunnusosio asiakaslomakkeelta. BorrowerUnwantedFields-asetuksella saa userid:n ja passwordin piiloon, mutta ei salasanan vanhenemispäivä-kenttää. Tosin, salasnan vanhenemispäivä -kenttä näkyy vain superlibrarian-oikeuksisille. */
body#pat_memberentrygen.pat #memberentry_userid.rows { display:none; }
```

### Piilota käyttäjänimi-kenttä salasananvaihto-sivulta

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/*Käyttäjänimi-kentän piilotus salasananvaihto-sivulla*/
/* /cgi-bin/koha/members/member-password.pl?member=?????? */
form[action="/cgi-bin/koha/members/member-password.pl"] ol li:nth-child(1) {
  display: none;
}
```

### Piilota Ensisijainen yhteydenottotapa -valinta asiakkaan muokkauksesta

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota Ensisijainen yhteydenottotapa -valinta asiakkaan muokkauksesta */
body#pat_memberentrygen.pat select#primary_contact_method.noEnterSubmit { display: none; }
body#pat_memberentrygen.pat label[for="primary_contact_method"] { display: none; }
```

### Piilota Muut määreet ja tunnukset -kohta asiakkaan muokkauksesta

Tällä piilotetaan asiakkaan muokkausnäytöltä Muut määreet ja tunnukset -osio. Tämä voi olla tarpeen, jos osion kaikki määreet on siirretty JS-rimpsuilla toiseen kohtaan lomaketta ja osio jää tyhjäksi. Huomioi, että kimpassa voi olla asiakasmääreitä, jotka näkyvät vain tietyille asiakastyypeille, jolloin osiota ei voi piilottaa.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Muut määreet ja tunnukset -kohta asiakkaan muokkauksesta. Tämä voi olla tarpeen, jos kaikki määreet on siirretty toiseen kohtaan lomaketta. Huomioi, että jotkin määreet saatetaan näyttää vain tietyillä asiakastyypeillä, jolloin piilotusta ei voi tehdä. */
body#pat_memberentrygen.pat fieldset#memberentry_patron_attributes.rows { display:none; }
```

---

### Piilota asiakastietojen Muita toimintoja -valikosta Päivitä lapsi aikuiseksi -vaihtoehto

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota asiakastietojen Muita toimintoja -valikosta Päivitä lapsi aikuiseksi */ 
body#pat_moremember.pat a#updatechild { display: none; }
```

### Piilota Verkkokirjasto-vaihtoehto Viestin lisäys -popupista

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Verkkokirjasto-vaihtoehto Viestin lisäys-popupista */
div#add_message_form #message_type option[value='B'] { display:none; }
```

### Piilota Sähköposti-vaihtoehto Viestin lisäys -popupista

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Sähköposti-vaihtoehto Viestin lisäys-popupista */
div#add_message_form #message_type option[value='E'] { display:none; }
```

### Piilota tekstiviesti numeroon -kenttä Asiakkaan viestiasetuksista asiakkaan muokkauksessa

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Tekstiviesti numeroon -kenttä Asiakkaan viestiasetuksista asiakkaan muokkauksessa */
body#pat_memberentrygen.pat #memberentry_messaging_prefs p { display:none; }
```

### Varaustunniste- ja Sotuavain-kenttien korkeus yhdeksi riviksi

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Varaustunnisteen ja sotuavaimen kenttien korkeus yhdeksi riviksi. Tarkista, että attribuuttien arvot vastaavat oman kimpan arvoja. */
#patron_attr_4 { height: 2em; }
#patron_attr_5 { height: 2em; }
```

### Piilota Perheen lainat -välilehti

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Tämä oli aiemmin JS-rimpsu, mutta muutettiin CSS:ksi versiossa 23.11.

```
/* Piilota Perheen lainat -välilehti */
#relatives-issues-tab { display: none; }
```

### Piilota Taattavien maksut -välilehti Tiedot-osiosta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Taattavien maksut -välilehti Tiedot-osiosta */
#guarantees_finesandcharges-tab { display: none; }
```

### Piilota taattavien maksut Tiedot-sivun Taattavat-listasta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota taattavien maksut Tiedot-sivun Taattavat-listasta */
#pat_moremember li.guarantees-fines { display: none; }
```

### Piilota Reklamaatiot-välilehti

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Kun nidepakettiasetukset laittaa päälle, tulee Nextillä näkyviin turhaan kaikille asiakkaille reklamaatiot-välilehdehti. Liittyy [tikettiin 142](https://github.com/KohaSuomi/Koha-23x/issues/142).

```
/* Piilota Reklamaatiot-välilehti asiakkaan Tiedot-sivulta*/
a#return-claims-tab { display:none; }
```

### Piilota Palauta valitut niteet -nappula asiakkaan lainat-taulussa

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Jos Palauta-sarake on piilossa, kannattaa myös Palauta valitut niteet -nappula piilottaa.
```
/* Piilota Palauta valitut niteet -nappula asiakkaan lainat -taulussa */
body#circ_circulation.circ button#CheckinChecked.btn.btn-default { display: none; }
body#pat_moremember.pat button#CheckinChecked.btn.btn-default { display: none; }
```

### Piilota asiakaslistat-välilehti Lainaus- ja Tiedot -osioista asiakkaan tiedoissa

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Asiakaslistat välilehden piilotus Lainaus- ja Tiedot-välilehdillä. */
a#pat_lists-tab { display:none; }
```

### Levennä otsikkokenttiä asiakkaan muokkauksessa

Asiakkaan muokkauksessa jotkin pitkät otsikoiden nimet menevät kentän taakse piiloon tai katkeaa oudosti. Tällä pystyy säätämään otsikkokentille lisää tilaa asikkaan muokkaussivulla. Oletusarvo on 10rem, tässä se on levennetty 13rem, voit muuttaa arvoa parhaaksi katsomaksesi arvoksi.

Huom. Tästä on olemassa tässä kirjastossa myös versio, jolla levennetään kaikkialla otsikkokenttien käytettävissä olevaa tilaa.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Levennä otsikkokenttiä asiakkaan muokkauksessa */
body#pat_memberentrygen fieldset.rows label { width: 13rem; }
```

### Piilota Lajittelu 1/2 -laatikot Takaajan haku -modaalissa

Liittyy [tikettiin #1330](https://github.com/KohaSuomi/Koha/issues/1330).

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Lajittelu 1/2 -laatikot Takaajan haku -modaalissa. */
body#pat_memberentrygen.modal-open form fieldset.brief ol li:nth-child(4),
body#pat_memberentrygen.modal-open form fieldset.brief ol li:nth-child(5) { display: none; }
```

### Piilota Väärä osoite ja Kortti kadonnut -rivit asiakkaan Tiedot-sivulta oikealta Kirjastotiedot-laatikosta

Liittyy [tikettiin #138](https://github.com/KohaSuomi/Koha-24.05/issues/138).

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Väärä osoite ja Kortti kadonnut -rivit asiakkaan Tiedot-sivulta oikealta Kirjastotiedot-laatikosta */
body#pat_moremember.pat li#patron-flags-gonenoaddress { display:none; }
body#pat_moremember.pat li#patron-flags-lostcard { display:none; }
```

### Lihavoi 'Tili on lukittu' huomautus asiakkaan Tiedot-sivulla

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Lihavoi 'Tili on lukittu' huomautus asiakkaan tiedoissa */
li.blocker.account_locked { font-weight: 700; }
```

### Lisää Tili on lukittu -huomauksen ja Tili on lukittu hallinnollisesti -ilmoituksen perään ohje vaihtaa PIN-koodi

Rimpsu lisää Tili on lukittu -huomauksen ja Tili on lukittu hallinnollisesti -huomautuksen perään virkailijalle muistutukseksi ohjeen vaihtaa PIN-koodi. Rimpsussa on kieliversio suomelle, ruotsille ja englannille.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Lisää käyttäjille ohjeeksi Asiakkaan infoboksiin Tili on lukittu ja Tili on lukittu hallinnollisesti-tekstin perään ": Vaihda PIN-koodi" */
html[lang='fi-FI'] >
body li.blocker.account_locked:after, html[lang="fi-FI"] >
body li.blocker.account_admin_locked:after {
  content: ": Vaihda PIN-koodi";
  color:#990000;
  }

/* Lisää käyttäjille ohjeeksi Asiakkaan infoboksiin Ditt konto är låst -tekstin perään ": Ändra PIN-koden" */
html[lang='sv-SE'] >
body li.blocker.account_locked:after, html[lang="fi-FI"] >
body li.blocker.account_admin_locked:after {
  content: ": Ändra PIN-koden";
  color:#990000;
  }

/* Lisää käyttäjille ohjeeksi Asiakkaan infoboksiin Account has been locked -tekstin perään ": Change PIN code" */
html[lang='en'] >
body li.blocker.account_locked:after, html[lang="fi-FI"] >
body li.blocker.account_admin_locked:after {
  content: ": Change PIN code";
  color:#990000;
  }
```

### Lihavoi asiakasmääre (varaustunnus) asiakkaan yhteenveto-osiossa vasemmalla

Tällä saa lihavoitua asiakkaan tiedoissa vasemman reunan infolaatikossa / yhteenveto-osiossa ensimmäisen asiakasmääreen, joka ainakin henkilöasiakkailla (aikuiset ja lapset) todennäköisesti on kaikilla varaustunnus, eli perimmäisenä tarpeena oli lihavoida asiakkaan varaustunnus. Muilla asiakastyypeillä lihavoiduksi voi tulla jokin muukin asiakasmääre.

Tarpeellisuus: Vapaaehtoinen <br />
Versio: 24.05

```
/* Asiakasmääre lihavoiduksi asiakkaan yhteenveto-osioon */
li.patronattribute:nth-child(1) { font-weight: bold; }
```



## Asiakkaat-sivu

### Säädä Selaa sukunimen mukaan -kohdan kirjaimet isommaksi ja harvemmaksi

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Säädä Selaa sukunimen mukaan -kohdan kirjaimet isommaksi ja harvemmaksi */
#pcard_members_search div.browse a,
body#pat_member.pat div.browse a {
  padding:0 0.35em;
  font-size:larger;
}
```

### Säädä Selaa sukunimen mukaan -kohdan kirjaimien taustaväri toiseksi, kun hiiri viedään kirjaimen kohdalle

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Säädä Selaa sukunimen mukaan -kohdan kirjaimien taustaväri toiseksi, kun hiiri viedään kirjaimen kohdalle */
#pcard_members_search .browse a:hover,
#pat_member .browse a:hover {
  background-color: #f3f4f4;
}
```

### Piilota asiakashaun "Kaikki"-vaihtoehto

Täällä pyritään estämään se, että virkailija ei vahingossa hae tietokannan kaikkia asiakastietoja listalle, jolloin kaikille listalla oleville tehdään muutoslokiin merkintä asiakastietojen katselusta.

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota asiakashaun "Kaikki"-vaihtoehto*/
#memberresultst_length select option:last-child { display: none; }
```

### Piilota Asiakkaan pikalisäys -painike

Rimpsu piilottaa Asiakkaan pikalisäys -painikkeen. Kyseisellä lomakkeella ei ole kaikkia tarvittavia kenttiä näkyvissä, joten se on ainakin osalle kimpoista turha.

Tarpeellisuus: Suositeltava<br />
Versio 24.05

```
/* Piilota Asiakkaan pikalisäys -nappi */
body#pat_member.pat div#quick-add-new-patron-button.btn-group { display: none; }
```

### Piilota asiakashausta valikosta Lajittelu-vaihtoehdot

Tarpeellisuus: Vapaaehtoinen<br />
Versio 24.05

```
/* Piilota asiakashausta valikosta Lajittelu-vaihtoehdot */
body#pat_member.pat select.searchfieldstype_filter option[value='sort1'] { display:none; }
body#pat_member.pat select.searchfieldstype_filter option[value='sort2'] { display:none; }

/* Piilota yläpalkin asiakashausta valikosta Lajittelu-vaihtoehdot */
div#header_search div#patron_search_panel div.form-extra-content select#searchfieldstype option[value='sort1'] { display:none; }
div#header_search div#patron_search_panel div.form-extra-content select#searchfieldstype option[value='sort2'] { display:none; }
```

---

## Lainaus ja palautus

### Lainaus ja palautus -osion etusivu

### Piilota uusinta-nappi

Piilota Lainaus ja palautus -osion etusivulta Uusinta-nappi. Toiminto ei noudata laina- ja maksusääntöjä, eikä ota huomioon varauksia, joten sitä ei kannata käyttää.

Versio: 24.05<br />
Tarpeellisuus: Suositeltava

```
/* Piilota uusinta-nappi lainaus- ja palautus -näkymässä */
body#circ_circulation-home a[href="/cgi-bin/koha/circ/renew.pl"] {
display: none;
}
```

### Piilota Myöhässä-raportti Lainaus ja palautus -sivulta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Myöhässä -raportti Lainaus ja palautus -sivulta */
body#circ_circulation-home.circ a[href*="/cgi-bin/koha/circ/overdue.pl"] {
display: none;
}
```

### Piilota Myöhässä ja maksuja -raportti Lainaus ja palautus -sivulta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Myöhässä ja maksuja -raportti Lainaus ja palautus -sivulta */
body#circ_circulation-home.circ a[href*="/cgi-bin/koha/circ/branchoverdues.pl"] {
display: none;
}
```

### Piilota Overdues/Myöhässä-otsikko  Lainaus ja palautus -sivulta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Jos ylemmät raportit piilotetaan, kannattaa myös otsikkorivi piilottaa.

```
/* Piilota Overdues/Myöhässä-otsikko Lainaus ja palautus -sivulta */
body#circ_circulation-home.circ div.col-sm-5.col-md-4 h3:nth-of-type(2) { display: none; }
```

### Piilota Overdues/Myöhässä- linkit ja -otsikko  Lainaus ja palautus -sivulta vasemman reunan valikosta

Myöhässä osion -piilotus, ensin otsikko, joka on määritelty järjestysnumerolla, eli jos otsikkojen järjestys muuttuu, niin saattaa joskus mennä sitten väärä otsikko piiloon.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Myöhässä-osio Lainaus ja palautus -sivuvalikosta */
body.circ div#navmenulist h5:nth-of-type(4),
body.circ div#navmenulist a[href="/cgi-bin/koha/circ/overdue.pl"],
body.circ div#navmenulist a[href="/cgi-bin/koha/circ/branchoverdues.pl"] { display: none; }
```

### Piilota Varausjono-linkki Lainaus ja palautus -sivulta ja vasemman reunan valikosta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Varausjono-linkki Lainaus ja palautus -sivulla */
a.circ-button[href="/cgi-bin/koha/circ/view_holdsqueue.pl"] { display: none;}

/* Piilota Varausjono-linkki Lainaus ja palautus -sivupalkista, jos valikko on käytössä */
div#navmenulist a[href="/cgi-bin/koha/circ/view_holdsqueue.pl"] {display: none;}
```

### Piilota Uusinta-linkki Lainaus ja palautus -sivun vasemman reunan valikosta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Uusinta-linkin piilotus Lainaus ja palautus -osion vasemman reunan valikosta */
div#navmenulist a[href*="/cgi-bin/koha/circ/renew.pl"] { display: none; }
```

### Piilota Noudettavissa olevat varaukset -raportilta Varaukset, joiden noutoaika on umpeutunut -välilehti

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota Noudettavissa olevat varaukset -raportilta Varaukset, joiden noutoaika on umpeutunut -välilehti */
body#circ_waitingreserves.circ a#holdsover-tab { display: none; }
```

### Lainaus

### Piilota "Älä lainaa ja tulosta kuitti" -nappula lainauksessa

Tarpeellisuus: Vapaaehtoinen<br />
Versio 24.05

```
/* Piilota Älä lainaa ja tulosta kuitti -nappula, jos yritetään lainata noudettava varaus toiselle asiakkaalle kuin varaajalle */
body#circ_circulation.circ button.print { display: none; }
```

### Piilota Automatic renewal / Automaattinen uusinta -checkbox

Versio: 21.11<br />
Versio: 22.11 Ei tarpeellinen, koska  AllowSetAutomaticRenewal -järjestelmäasetuksella saa täpän piiloon.

```
/* Automatic renewal / Automaattinen uusinta -checkboxi piiloon */
body#circ_circulation #set-automatic-renewal { display: none; }
```

### Palautus

### Piilota palautus-näytön asetukset

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota Palautukset-sivulla palautusasetukset - varmista, ettei piilota muita vastaavia asetussäätöjä. */
body#circ_returns.circ i.fa-solid.fa-sliders { display: none; }
body#circ_returns.circ div#forgive-overdue-fines.circ-setting { display: none; }
body#circ_returns.circ div#book-drop-mode.circ-setting { display: none; }
body#circ_returns.circ div.forgive-manual-hold-fees.circ-setting { display: none; }
```

### Piilota asiakkaan tiedot varaus-popupeista

Jotta turhia asiakastietojen katseluita saadaan vähennettyä, piilotetaan palautuksessa asiakkaan yhteystiedot varausten popupeista. Rimpsuista on kaksi eri versiota ja niitä käytetään riippuen siitä, onko käytössä varausten automaattinen kiinni jääminen vai ei.

Tarpeellisuus: Pakollinen<br />
Versio: 24.05

Varausten automaattinen kiinnijääminen päällä. HUOM! Alimmainen rivi korjattu toisenlaiseksi, koska aiempi versio piilotti palautuksessa oikean yläreunan valikosta kirjastovalinnan. Uudella versiossa piilottuu sähköpostiosoite, mutta laatikkoon jää näkyville listapallero.

```
/* Piilota varausruudusta asiakkaan yhteystiedot, kun käytössä automaattinen varauksen kiinni jääminen */ 
body#circ_returns.circ div.dialog.message.hold-auto-filled ul li:nth-child(4) { display: none; } /* Varaus palautuskirjastossa, puhelinnumero piiloon */
body#circ_returns.circ li.patronaddress1 { display: none; } 
body#circ_returns.circ li.patroncity { display: none; } 
body#circ_returns.circ a#boremail { display: none; }
```


Varausten automaattinen kiinnijääminen ei ole päällä

```
/* Piilota varauksen popparista asiakkaan yhteystiedot, kun varausten automaattinen kiinni jääminen ei ole päällä. */
body#circ_returns.circ.modal-open ul li:nth-child(4) { display: none; } /* Varaus palautuskirjastossa, puhelinnumero piiloon */
body#circ_returns.circ.modal-open ul li:nth-child(5) { display: none; }  /* Kuljetettava muualle, sähköpostiosoite piiloon */
body#circ_returns.circ.modal-open li.patronaddress1 { display: none; } /* Osoite piiloon */
body#circ_returns.circ.modal-open li.patroncity { display: none; } /* Osoite piiloon */
body#circ_returns.circ.modal-open a#boremail { display: none; } /* Varaus palautuskirjastossa, sähköpostiosoite piiloon */
body#circ_returns.circ div.modal-content li.notification_method { display: inline-block !important; } /* Palautetaan näkyville Ilmoitus asiakkaalle, jos kaksi ensimmäistä piilotusta piilottavat sen puhelinnumeron ja/tai sähköpostin puuttumisen takia */
```

### Laskutettu-merkintä palautuksessa isommaksi

Jos palautetaan laskutettu nide, siitä näkyvä ilmoitus on pieni. Alla olevalla css-säädöllä Laskutettu-ohjeistuksen kokoa saa säädettyä isommaksi.

Lisätty: 28.12.2022<br />
Tekijä: Anni Rajala<br />
Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Säädä Laskutettu-merkintä palautuksessa huomautuksessa isommaksi */
p.problem.ret_nflupdate { font-weight: 500; font-size: 22px; }
```

### Piilota varauksen palautuspopparista Älä huomioi -nappi

Tarpeellisuus: Suositeltava<br />
Versio: 22.11

```
/* Piilota varauksen palauttamisen yhteydessä popparista Älä huomioi -nappi (kun käytössä HoldsAutoFill-järjestelmäasetus) */
/* ja jo noudettavana olevan varauksen uudelleenpalautuksen yhteydessä popparista Poista varaus -nappi ja Peru kuljetus -nappi */
body#circ_returns.circ.modal-open button.btn.btn-default.deny { display: none; }
```

Versio: 24.05

Vaihtoehtoinen versio, joka piilottaa myös Peruuta varaus -napin ja Peru kuljetus -napin.

```
/* Piilota varauksen palauttamisen yhteydessä popparista Älä huomioi -nappi, noudettavana olevan varauksen palautuksen yhteydessä popparista Poista varaus -nappi ja Peru kuljetus -nappi. Käytössä on varausten automaattinen kiinni jääminen. */
body#circ_returns.circ.modal-open button.btn.btn-default { display: none; } 
body#circ_returns.circ.modal-open button.btn.btn-default.deny.cancel-hold { display: none; } 
body#circ_returns.circ.modal-open button.btn.btn-default.approve { display: initial; }
body#circ_returns.circ.modal-open button.btn.btn-default.print { display: initial; }
body#circ_returns.circ.modal-open button.btn.btn-default.deny { display: initial; }
body#circ_returns.circ.modal-open button.btn.btn-default.submit.openWin { display: initial; }
```

Versio 24.05

Jos käytössä on nidepaketit, kannattaa edelliseen rimpsuun lisätä vielä loppuun tämä, jotta nidepaketin palautuksessa näkyvät Vahvista palautus ja Merkkaa puuttuvat niteet kadonneiksi -napit.

```
body#circ_returns.circ.modal-open div#bundle-needsconfirmation-modal.modal.fade.audio-alert-action.block.in button.btn.btn-default { display: initial; } /* Tuo näkyville nidepaketin palautuksessa Vahvista palautus ja merkkaa puuttuvat niteet kadonneiksi -nappi. Se piilottuu ensimmäisen rimpsun vuoksi */
```

Versio 24.05

Jos niteen kuljetuksen vahvistuspopparista puuttuu yllä olevien rimpsujen vuoksi OK- ja Tulosta kuitti -napit, saa ne näkyville tällä, jos TransfersBlockCirc-järjestelmäasetuksessa **estetään** ilmoituksen ohittaminen:
```
body#circ_returns.circ.modal-open div#item-transfer-modal.modal.fade.audio-alert-action.noblock.in button.btn.btn-default { display: initial; } /* Tuo näkyville Ok- ja Tulosta kuitti -napit kun nide pitää kuljettaa palautuksessa. Se piilottuu ensimmäisen rimpsun vuoksi. TransfersBlockCirc-järjestelmäasetuksessa estetään ohitus. */
```

Jos niteen kuljetuksen vahvistuspopparista puuttuu yllä olevien rimpsujen vuoksi OK- ja Tulosta kuitti -napit, saa ne näkyville tällä, jos TransfersBlockCirc-järjestelmäasetuksessa **ei estetä** ilmoituksen ohittaminen:

```
body#circ_returns.circ.modal-open div#item-transfer-modal.modal.fade.audio-alert-action.noblock.in button.btn.btn-default { display: initial; } /* Tuo näkyville Ok- ja Tulosta kuitti -napit kun nide pitää kuljettaa palautuksessa. Se piilottuu ensimmäisen rimpsun vuoksi. TransfersBlockCirc-järjestelmäasetuksessa ei estetä ohitus. */
```

---

## Maksut

### Piilota Maksa- ja Poista-alavälilehdet asiakkaan maksusivulta

Tarpeellisuus: Ei tarpeellinen

```
/* Piilota Maksa-Poista välilehdet Maksusivulta */
body#pat_paycollect ul.nav-pills { display: none; }
```

### Piilota Luo hyvitys -välilehti asiakkaan maksuista 

Tarpeellisuus: Hyvin suositeltava<br />
Versio: 24.05

```
/* Piilota Luo hyvitys -välilehti asiakkaan maksuista */
li.manualcredit { display: none; }
body#pat_paycollect.pat a[href*="/cgi-bin/koha/members/mancredit.pl"] {
  display: none;
}
```

### Piilota oletusmaksuja asiakkaan lisää maksu -toiminnosta

Maksutyyppien näkyvyyttä voi muokata myös Ylläpidossa Maksutyypit-osiossa. Jos maksutyypiltä ottaa pois rastin Voidaan lisätä maksu käsin? -kohdasta, niin se katoaa Lisää maksu -välilehdeltä.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota maksutyyppejä asiakkaan lisää maksu -toiminnosta */
body#pat_maninvoice.pat option[value='NEW_CARD'] { display:none; }
body#pat_maninvoice.pat option[value='LOST'] { display:none; }
```

### Piilota asiakkaan Maksut/Tapahtumat-välilehdeltä Luo hyvitys, alennus, peruuta veloitus ja mitätöi maksutapahtuma -painikkeet

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota alennus, peruuta veloitus, luo hyvitys ja mitätöi maksutapahtuma -napit asiakkaan tilitapahtumat sivulta */
body#pat_borraccount button.discount-action { display: none; }
body#pat_borraccount button.cancel-action { display: none; }
body#pat_borraccount button.refund-action { display: none; }
body#pat_borraccount button.void-action { display: none; }
```

### Piilota asiakkaan Maksut/Tapahtumat-välilehdeltä Tulostus- ja Maksu-nappi

Piilota Maksut/Tapahtumat-välilehdeltä maksun tietojen tulostus-napit sekä Maksu-nappi. Liittyy tikettiin [Koha #476](https://github.com/KohaSuomi/Koha/issues/476).

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
body#pat_borraccount a.btn.btn-default.btn-xs.invoice-print-action { display: none; } /* Maksun tietojen tulostus-napin piilotus Tapahtumat-välilehdeltä */
body#pat_borraccount button.btn.btn-default.btn-xs.pay-action { display: none; } { display: none; } /* Maksa-napin piilotus Tapahtumat-välilehdeltä */
body#pat_borraccount a.btn.btn-default.btn-xs.receipt-print-action { display: none; } /* Maksutapahtuman tai maksun poiston kuitin tulostuksen piilotus Tapahtumat-välilehdeltä */
```

### Piilota Poista-välilehden linkki Maksu-sivulta kun maksetaan valittuja maksuja

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Poista-välilehden linkki Maksu-sivulta kun maksetaan valittuja maksuja. */
body#pat_paycollect ul.nav-pills { display: none;}
```


## Tiedonhaku

### Tasaa otsikko ja tieto perustiedot-näytöllä samalle tasolle

Tarpeellisuus: Ei tarpeen versiosta 23.11 lähtien<br />
Versio: 22.11

```
/* Tasaa otsikko ja tieto perustiedot-näytöllä samalle tasolle */
.label { vertical-align: inherit; }
```


### Fonttikokojen säätö isommaksi koko perustiedot-näytöllä

Tarpeellisuus: Vapaaehtoinen, käytä mielummin selaimen ctrl+ -toimintoa suurentamaan fontteja<br />
Versio: 21.11

```
/* Säädä perustiedot-näytön fonttikokoja isommaksi*/
#catalogue_detail_biblio { font-size:larger; }
```

### Otsikkorivin fonttikoko suuremmaksi

Tarpeellisuus: Ei tarpeen enää versiossa 22.11<br />
Versio: 21.11

```
/* Otsikkorivin (nimeke ja tekijä) fonttikoko suuremmaksi */
#catalogue_detail_biblio h1 { font-size: 16pt; }
```

### Seuraava- ja Edellinen -linkit pienemmiksi

Versio: 17.05, ei tarpeellinen versiossa 21.11, koska linkit muuttuneet nuoliksi

```
/* Seuraava- ja edellinen-linkit pienemmiksi, jotta ne mahtuvat niille sallittuun tilaan */
body#catalog_detail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff; }
body#catalog_MARCdetail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff;}
body#catlaog_labeledMARCdetail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff;}
body#catalog_moredetail div.browse-prev-next { font-size:8.5pt; background-color:#ffffff;}
```


### Piilota kentät 336-338

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota perustiedot-näytöltä kentät 336-338 */
body#catalog_detail #content_type.results_summary { display: none; }
```

### Esityskokoonpanon järjestys näytöllä

Tarpeellisuus: Ei tarpeellinen version 17.05 jälkeen<br />
Versio: 17.05

```
/* Esityskokoonpanon järjestys näytöllä */
.performance-medium span[class^="sf-"] + span[class^="sf-"]:before {
  content: ", ";
}
```

### Otsikot boldattuna mustalla

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Rivien otsikot boldilla perustiedot-näytöllä. selkeyttää näkymää. */
.results_summary .label { color: #333; font-weight: bold }
body#catalog_detail.catalog h5.author { font-weight: bold }
```

### Boldaa hakutuloslistan ja Osakohteet-välilehden nimekkeet/otsikot

Liittyy tikettiin [#1395](https://github.com/KohaSuomi/Koha/issues/1395)

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Boldaa hakutuloslistan ja Osakohteet-välilehden nimekkeet/otsikot */
#catalog_results #searchresults a.nimeke { font-weight: bold }
#bibliodetails #components a.nimeke { font-weight:bold; }
```


### Auktoriteettien MARC-näkymän säätöä

Tarpeellisuus: Ei tarpeellinen<br />
Versio: 17.05

```
/* Auktoriteettien MARC */
#authoritiestabs div.tag p { font-weight: normal; display: inline; font-family: monospace; }
#authoritiestabs div.tag .labelsubfield,
#authoritiestabs div.tag .labelsubfield b { font-weight: normal; font-family: sans-serif; }
#authoritiestabs div.tag .labelsubfield span { display:none; }
#authoritiestabs div.tag p .labelsubfield:hover span,
#authoritiestabs div.tag p:hover .labelsubfield span {  display: inline; float:right; border: 1px solid black; background-color:#f0f0f0; position:relative; top: -1em; right: 0; padding:1em; }
```

### Muokkaa hakutulos-näytön värejä

Tarpeellisuus: Ei tarpeellinen<br />
Versio: 17.05

```
/* Muokkaa hakutulos-näytön värejä */
.results_summary { color: #000111 !important; }
.results_summary span { color: #000000; font-weight: normal !important; }
.results_summary .label { color: #000000 !important; }
```

### Piilota Näytä kausijulkaisun tiedot -linkki

Tarpeellisuus: Ei tarpeellinen<br />
Versio: 17.05

```
span.results_summary.analytics { display: none; }
```

### Piilota perustiedot-näytöltä Osakohteet ja Näytä osakohteet -kohta kuvailutietojen osiosta

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05


```
/* Piilota perustiedot-näytöltä Osakohteet ja Näytä osakohteet -kohta kuvailutietojen osiosta. */
body#catalog_detail span.results_summary.analytics.analytic_monograph { display: none; }
body#catalog_detail span.results_summary.analytics.analytic_undefined { display: none; }
```

### Piilota Huomautus toimenpiteistä

Piilota perustiedot-näytöltä huomautus toimenpiteestä eli MARC-kentän 583-tieto.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Toimenpide-huomautus 583-kenttä perustiedot-näytöltä */
span.results_summary.actionnote { display: none; }
```

### Piilota tuplakansikuvat

Joskus luettelointitiedoissa on syystä tai toisesta useampi kansikuvalinkki. Jos haluaa, että näkyvillä on vain yksi kansikuva, saa muut piiloon seuraavalla rimpsulla.

Tarpeellisuus: Ei tarpeellinen <br />
Versio: 17.05

```
/* Piilota tuplakansikuvat */
.cover_image_container ~ .cover_image_container {
   display:none;
}
```


### Säädä kansikuvan kokoa

Alla on kolme versiota, joilla voi säätää kansikuvien kokoa. Ensimmäinen versio vaikuttaa sekä hakutuloslista-sivulle että perustiedot-sivulle. Toinen vaikuttaa vain hakutulostilsta-sivulle ja kolmas perustiedot-näytölle. 

Tarpeellisuus: Suositeltava<br />
Versio 24.05


Hakutuloslistalle:
```
/* Säädä hakutuloslistan kansikuva tietyn kokoiseksi. Muuta pikselikoko tarvittaessa toiseksi. */ 
body#catalog_results.catalog img { max-width: 200px; }
```

Perustiedot-näytölle:
```
/* Säädä perustiedot-näytön kansikuva tietyn kokoiseksi. Muuta pikselikoko tarvittaessa toiseksi. */ 
body#catalog_detail.catalog div#custom-coverimg.cover-image { height: 380px; width: 300px; }
body#catalog_detail.catalog div#biblio-cover-slider.cover-slider.cover-slides { height: 380px; width: 300px; }
body#catalog_detail.catalog img#custom-img { height: 90%; max-width: 180% }
```

### Piilota kansikuva-sarakkeen teksti hakutuloksista

Tarpeellisuus: Vapaaehtoinen<br />
Versio 24.05

```
/* Piilota kansikuva-sarakkeen tekstit hakutuloksista */
body#catalog_results.catalog div.no-image {display: none;}
body#catalog_results.catalog td.bookcoverimg div.hint {display:none;}
```

### Piilota tarkassa haussa Lisärajaukset-osio

Tarpeellisuus: Vapaaehtoinen (huom. jos tämän piilottaa, menee piiloon osa indeksointityöryhmän päättämistä hakurajausvaihtoehdoista)<br />
Versio: 24.05

```
/* Tarkan haun Lisärajuslaatikon piilotus. Jos tämän laittaa päälle, menettää valikoihin lisätyt hakuehdot */
#catalog_advsearch #subtype { display:none; }
```

### Piilota nidehaussa Inventaarionumero-sarake

Tarpeellisuus: Vapaaehtoinen<br />
Versio 24.05

```
/* Piilota inventaarionumero-sarake nidehaun tuloksissa */
body#catalog_itemsearch.catalog td:nth-child(14) { display: none; }
body#catalog_itemsearch.catalog th#item_inventoryno { display: none; }
```

### Piilota Nidetyyppi-sarake korissa

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Nidetyyppi-sarake korissa */
#cart_basket th:nth-child(3),
#cart_basket td:nth-child(3) { display: none; }
```

### Piilota Niteet-sivulta Piilota sija jonossa -kohta tai Ennakkovarattavissa-rivi

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Tämä piilottaa Niteet-sivulta koko Piilota Sija jonossa -kohdan eli piiloon menee Jätä pois paikallistan varausten jonosta ja Ennakkovarattavissa -kohdat. Alla vaihtoehto.
```
/* Piilota Sija jonossa -kohta Niteet-sivulla */
body#catalog_moredetail div.page-section:not(:first-child) div.listgroup:nth-child(3) { display: none; }
```

Tai jos haluaa piilottaa vain Ennakkovarattavissa-kohdan, niin voi käyttää tätä:
```
/* Piilota Ennakkovarattavissa -kohta Niteet-sivulla */
body#catalog_moredetail div.page-section:not(:first-child) div.listgroup:nth-child(3) li:nth-child(2) { display: none; }
```

### Muuta MARC21-kenttien otsikot näkymään isoilla kirjaimilla

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Tällä rimpsulla voi muuttaa Tietueen MARC21-näkymässä ja tietueen muokkauksessa MARC21-kenttien otsikot näkymään isoilla kirjaimilla (ei siis varsinaisesti muuta, näyttää vain). Voi selkeyttää näkymää jonkin verran.

```
/* Isoiksi kirjaimiksi MARC21-kenttien otsikot */
body#catalog_MARCdetail.catalog div.tag_title, body#cat_addbiblio.cat a.expandfield  {
        text-transform: uppercase; }
```

### Säädä Kokoelmat-taulukossa alasvetovalikoiden leveys kapeammaksi

Liittyy [tikettiin #139](https://github.com/KohaSuomi/Koha-24.05/issues/139).

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Säädä Kokoelmat-taulukossa alasvetovalikoiden leveys kapeammaksi. Valikot tulevat näkyville, kun klikkaa Näytä rajaukset -linkkiä */
body#catalog_detail.catalog select.dt-select-filter { max-width: 200px; }
```

### Säädä Nidetyyppi-sarakkeen maksimileveys lisäksi kapeammaksi kuin muilla sarakkeilla "Säädä Kokoelmat-taulukossa alasvetovalikoiden leveys kapeammaksi

Liittyy [tikettiin #139](https://github.com/KohaSuomi/Koha-24.05/issues/139) ja voi laittaa yllä olevan alasvetovalikoiden säädön lisäksi, jos haluaa säätää Kokoelmat-taulukon nidetyyppi-saraketta kapeammaksi kuin muita sarakkeita.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Säädä Nidetyyppi-sarakkeen maksimileveys lisäksi kapeammaksi kuin muilla sarakkeilla "Säädä Kokoelmat-taulukossa alasvetovalikoiden leveys kapeammaksi" -rimpsussa. */
body#catalog_detail.catalog th#holdings_itype { max-width: 100px; }
body#catalog_detail.catalog th#holdings_itype select.dt-select-filter { max-width: 100px; }
```

### Säädä Kokoelmat-taulukossa Tila-sarakkeelle miminileveys

Liittyy [tikettiin #139](https://github.com/KohaSuomi/Koha-24.05/issues/139).

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Säädä Kokoelmat-taulukossa Tila-sarakkeelle miminileveys, jotta taulukko ei veny kovin pitkäksi. */
body#catalog_detail.catalog td.status { min-width: 250px;}
```

### Lisää nidehakuun huomautus <>-operaattoreiden katkaisusta Viivakoodi-valikon alle

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Lisää nidehakuun huomautus <>-operaattoreiden katkaisusta Viivakoodi-valikon alle. */ 
body#catalog_itemsearch.catalog p.hint:nth-child(2):after { content: " \00a0 Vuosilukuja ei voi katkaista, jos käyttää <>-operaattoreita"; color:red; }
```

---

## Varaukset

### Lisää varauksenteko-sivulle huomautus valita noutokirjasto niteen kohdalta, jos tehdään nidevaraus

Tämä ei ole enää kovin tarpeellinen versiossa 24.05, koska varaussivulla ei ole enää yläreunassa noutokirjaston valintaa. Se tehdään aina joko seuraava vapaa nide -kohdassa tai nidevarauksen kohdalla.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/* Lisää varauksenteko-sivulle huomautus valita noutokirjasto niteen kohdalta, jos tehdään nidevaraus. */
body#circ_request.catalog div#requestspecific_filter:after {
  content: " Valitse noutokirjasto niteen kohdalta, jos teet nidevarauksen.";
  color:red;
}
```

### Piilota varauksen teko -sivulta asiakkaiden selaaminen sukunimen mukaan

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota varauksen teko -sivulta asiakkaiden selaaminen sukunimen mukaan */
body#circ_request.catalog div.browse { display: none; }
```

### Piilota Näytä aina varaukset -täppä varauksen teko -sivulla

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota "Näytä aina varaukset" -täppä varauksenteko-sivulla, koska se ei toimi Koha-Suomi-muutosten vuoksi. */
body#circ_request.catalog label[for="always_show_holds"] { display:none; }
body#circ_request.catalog input#always_show_holds { display:none; }
body#circ_request.catalog a#show_holds_now.btn.btn-default { display:none; }
```

### Säädä, kuinka leveä näytön pitää olla, jotta taulukoista piilotetaan sivulta toiselle siirtyminen

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Säädetään sitä, kuinka leveä näytön pitää olla, että taulukoista piilotetaan siirtyminen sivulta toiselle sivunumeroiden perusteella esim. varaustenteko-sivulla. Eli piilotetaan numerolinkit. */
@media only screen and (min-width: 1000px) {
    .dataTables_wrapper
        .dataTables_paginate
            span
                .paginate_button,
    .dataTables_wrapper
        .dataTables_paginate
            span
                .ellipsis {
                    display: inline-block;
                }
}
```

### Varauksen keskeytyksen korostus punaiseksi

Kun varaus on keskeytetty, muuttuu tällä säädöllä teksti keskeytetty-teksti punaiseksi ja keskeytys on helpompi havaita.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Varausten keskeytyksen korostus punaikseksi tietueen varaukset-sivulla */ 
#circ_request.catalog button[data-suspended="true"] + label { color:red; font-weight:bold !important;}
```

### Piilota monivarauksen teossa ensimmäinen sarake eli valintatäpät

Monivarauksen teossa valintaruudut eivät vaikuta siihen, tehdäänkö varaus teokseen vai ei, joten ne päätettiin piilottaa. Liittyy [tikettiin #780](https://github.com/KohaSuomi/Koha/issues/780).

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Piilota valintaruudut (1. sarake) monivarauksessa (request.pl) */
#requesttitles th:first-child,
#requesttitles td:first-child { display: none; }
```

### Piilota Noudettavissa olevat varaukset -raportilta Varaukset, joista asiakas on tehnyt poistopyynnön

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota Noudettavissa olevat varaukset -raportilta Varaukset, joista asiakas on tehnyt poistopyynnön */
body#circ_waitingreserves.circ a#holdscancelled-tab { display: none; }
```

### Piilota varauksenteko-sivulta viimeinen Tulosta kuitti -sarake

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Piilota varauksenteko-sivulta Tulosta kuljetuskuitti -sarake taulukosta */
body#circ_request.catalog table#holds-queue.holds_table.dataTable.no-footer th:nth-child(13) { display: none; }
body#circ_request.catalog table#holds-queue.holds_table.dataTable.no-footer td:nth-child(13) { display: none; }
```

---

## Kausijulkaisut

### Tasaa kausijulkaisujen vastaanotossa nidetiedot keskemmälle ruutua

Tarpeellisuus: Ei enää tarpeen versiosta 23.11 lähtien<br />
Versio: 22.11

```
/* Tasaa kausijulkaisujen vastaanotossa nidetiedot keskemmälle ruutua. */
body#ser_serials-edit.ser fieldset.rows ol li {display:block;}
body#ser_serials-edit.ser fieldset.rows ol li label {float: left; font-weight: 700; margin-right: 1rem; text-align: right;}
```

---

## Muita

### Muuta kaikissa taulukoissa rivin taustaväri, kun hiiri viedään rivin kohdalle

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

```
/* Muuta kaikissa taulukoissa rivin taustaväri, kun hiiri viedään rivin kohdalle. */
tr:hover td { background-color:#f8fcf6 !important; }
```

### Korjataan päivämääräkentän leveys sopivaksi

Tarpeellisuus: Ei enää tarpeen versiosta 23.11 lähtien.<br />
Versio: 22.11

```
/* Korjataan päivämääräkenttien leveys sopivaksi. Tiketit 111 ja 119 */
.flatpickr-input {width: auto}
```

### Koha-logon piilotus virkailijaliittymän vasemmasta reunasta

Versio: 24.05

```
/* Yläkulman Koha-logon piilotus */
.navbar-brand > img {
    display:none;
}
```

### OpenDocument-vaihtoehdon piilotus raporteista

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* OpenDocumentin piilotus raporteista */
body#rep_guided_reports_start.rep button#format + ul li:nth-child(3){display: none;}
```

### Kimpan logo näkyviin yläpalkkiin

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Kimpan logo näkyviin yläreunaan */
/* Logon lisääminen base64-muodossa vasempaan reunaan yläpalkkiin ja Koha-logon piilotus. Logon saa muutettua base64-muotoon verkosta löytyvillä työkaluilla, hae hakukoneella image to base64 ja valitse jokin työkalu ja muunna kimpan logokuva sillä koodiksi. Kopioi koodi ja vaihda se tässä olevan koodin tilalle. */
#logo.navbar-brand:after {
  background: url(data:image/png;base64,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);
  background-size: 82px 20px;  
  display: block;
  width: 82px; 
  height: 20px;
  content:"";
}

/* Yläkulman Koha-logon piilotus */
.navbar-brand > img {
    display:none;
}
```

### Musta yläpalkki leveämmäksi

Tällä saa säädettyä mustan yläpalkin leveämmäksi, mutta huomioi, että se vaikuttaa myös alareunan palkin leveyteen samalla.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Musta yläpalkki leveämmäksi - tarvittaessa vain */
.navbar {
  height: 45px;
}
```

### Lisää kimpan logo kirjautumissivulle

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Kimpan logo kirjautumissivulle base64-muodossa. Muista tehdä koodi oman kimpan logosta ja vaihtaa se rimpsuun, tässä esimerkissä on Vaaran logo.
```
/* Lisää kimpan logo kirjautumis-sivulle */
#login h1{
background:  url('data:image/png;base64,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');
background-repeat: no-repeat;
background-position: center;
background-size: contain;
background-repeat: no-repeat;
}
```

### Piilota Työkalut-sivulta linkit JS-liitännäisiin Työkaluliitännäiset-osiosta

Tarpeellisuus: Ei tarpeen, muutettu JS-rimpsuksi<br />
Versio: 23.11

```
/* Piilota Työkalut-sivulta linkit JS-liitännäisiin Työkaluliitännäiset-osiosta. Rimpsut piilottavat tietyn rivin, joten kun liitännäisiä tulee lisää, kopioi yksi riveistä ja muuta nth-child(1)-kohtaan sopiva rivinumemero. JS-liitännäiset pitäisi tulla peräkkäin, mutta testaamalla löytyy oikea numero. */
body#tools_tools-home.tools div.col-sm-6 li:nth-child(1) { display: none; }
body#tools_tools-home.tools div.col-sm-6 li:nth-child(2) { display: none; }
```

### Piilota niteiden eräajosta 'Muut määreet - Jätä pois paikallisten varausten jonosta' ja 'Palauta niteet'

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Tästä on kaksi eri versiota, joista toinen toimii uudemmilla Firefox-selaimilla ja toinen vanhemmilla.

Tämä toimii vanhemmilla Firefox-versiolla kuin 121. Käytä tätä, jos et ole varma, että kaikilla käyttäjillä on uudempi versio.
```
/* Piilota niteiden eräajosta 'Muut määreet - Jätä pois paikallisten varausten jonosta' ja 'Palauta niteet' */
body#tools_batchMod-edit div#cataloguing_additem_newitem
fieldset.rows:nth-child(4),
body#tools_batchMod-edit div#cataloguing_additem_newitem
fieldset.rows:nth-child(5) { display:none; }
```

Tämä toimii vain Firefox-versiosta 121 alkaen.
```
/* Piilota niteiden eräajosta 'Muut määreet - Jätä pois paikallisten varausten jonosta' ja 'Valinnat - Palauta niteet' */
body#tools_batchMod-edit fieldset:has(select#exclude_from_local_holds_priority),
body#tools_batchMod-edit fieldset:has(select#mark_items_returned) { display: none; }
```

### Piilota Uusi/Renew-vaihtoehto yläpalkista

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

Muutettu JS-rimpsusta CSS-rimpsuksi versiossa 23.11.

```
/* Piilota Uusi/Renew-vaihtoehto yläpalkista */
a#renew_search-tab { display: none; }
```

### Levennä otsikkokenttiä

Monesti otsikkokentille on määritetty liian vähän tilaa, jolloin pitkät suomalaiset sanat joko piilottuvat tekstikentän alle tai katkeavat oudosti. Tällä rimpsulla saa säädettyä otsikkokentille lisää tilaa leveyssuunnassa. Oletusarvo on 10rem, tässä se on säädetty 13rem. Voit myös valita jonkin muun sopivan arvon.

Huom! Tästä rimpsusta on olemassa tässä kirjastossa myös versio, jolla säädetään otsikkokenttien leveyttä vain asiakkaan muokkaussivulla.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/* Levennä otsikkokenttiä */
fieldset.rows label { width: 15rem; }
```

### Piilota Esikatsele SQL -vaihtoehto valikosta Tallennetuissa raporteissa

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

Piilotetaan tallennetuista raporteista raportin kohdalla olevasta valikosta Esikatsele SQL -vaihtoehto, koska modaalissa olevat napit eivät kaikki noudata käyttäjäoikeuksia. Liittyy [tikettiin #1346](https://github.com/KohaSuomi/Koha/issues/1346).
```
/* Piilota Esikatsele SQL -vaihtoehto valikosta Tallennetuissa raporteissa */
body#rep_guided_reports_start.rep a.preview_sql { display: none; }
```

### Säädä tallennetuissa raporteissa Muokkaa-valikon asettelu nätimmäksi

Tarpeellisuus: Suositeltava<br />
Versio: 24.05

Huom! Tähän on tulossa yhteisössä uudemmassa versiossa korjaus, joten tästä voitaneen luopua seuraavassa versionpäivityksessä (ei tässä 24.05:een päivityksessä siis)
```
/* Säädä tallennetuissa raporteissa Muokkaa-valikon asettelu nätimmäksi */
.dropdown-menu > li > form > a {
  display: block;
}
```
---

### Testiympäristön ulkoasun muutokset

Versio: 21.11

```
.gradient {
background-image: -webkit-gradient( linear, left top, left bottom, color-stop(0.1, rgb(255, 241, 186)), color-stop(0.99, rgb(255,255,255)) );
}

#header.navbar-default {
background: rgb(255, 241, 186);
}

#breadcrumbs {
background-color: #e3f2c8;
}

#searchheader {
background-color: #e3f2c8;
}

.navbar .nav > li > a {
color: #405b0e;
}

#menu ul > li > a {
background: linear-gradient(180deg,#e3f2c8 0,#e3f2c8 96%,#c1c1c1);
}

.ui-tabs .ui-tabs-nav li {
background: #e3f2c8 none;
}

fieldset {
  background-color: #fafde9;
}

ul.biglinks-list li a.icon_general {
border: solid 2px #b8ce97;
background-color: #fafbf4;
}

body {
background-color: #fff2dd;
}
```
