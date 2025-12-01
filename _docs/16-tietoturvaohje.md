---
title: 'Koha-Suomen tietoturvaohje'
permalink: /dokumentaatio/tietoturvaohje/
redirect_from:
  - /theme-setup/
toc: true
---

Tällä sivulla on kirjastoille tarkoitettuja ohjeita ja hyviä käytäntöjä Koha-järjestelmän tietoturvasta ja turvallisuudesta huolehtimiseen.

## Koha-Suomen tietosuoja- ja turvaperiaatteet

[Koha-Suomen tietosuoja- ja turvaperiaatteet](/dokumentaatio/tietosuojaperiaatteet/) omalla sivullaan.

## Yleistä

Koha-käyttöön suositeltava selain on Firefox ESR (Extended Support Release). Selainta on Kohaa käytettäessä hyvä käyttää yksityisen selauksen tilassa (Private Browsing). Kuten normaalia, linkkien seuraamisessa tulee noudattaa varovaisuutta eikä "epämääräisiä" linkkejä tule koskaan avata.

## Pääsy Kohaan

Virkailijaliittymiin pääsy on rajattu vuosittain uusittavin asiakasvarmentein. Koha-Suomi toimittaa varmenteet kimpan pääkäyttäjälle Matrix-viestialustalla. Varmenne tulee asentaa sellaisten koneiden selaimiin joilla Kohaa halutaan käyttää. Varmennetta tai sellaisella varustettua selainta ei tule luovuttaa sellaisten henkilöiden käyttöön, joilla ei ole oikeutta käyttää Kohaa. Tästä voidaan huolehtia esimerkiksi erillisillä käyttäjäprofiileilla oikeudellisille ja oikeudettomille käyttäjille. Pääsääntöisesti Kohaa tulisi käyttää ainoastaan työnantajan toimittamilla laitteilla ja laitteiden tietoturvasta tulee huolehtia asianmukaisesti.

Asiakasvarmenteen asennusohje: [Kohan_asiakasvarmenne_asennusohje_2024.pdf](https://github.com/user-attachments/files/17023177/Kohan_asiakasvarmenne_asennusohje_2024.pdf)

Kirjastokorttien ja virkailijatunnusten tulee lukittua jos salasana syötetään liian monta kertaa väärin. Tällä tavoin voidaan varsin tehokkaasti estää tunnuksiin tai kirjastokorttinumeroihin kohdistuva väsytyshyökkäys. Kohassa lukkiutumista säätää järjestelmäasetus _FailedLoginAttempts_, joka täytyy asettaa mielekkääseen arvoon (suosittelemme arvoa väliltä 3-5). Tunnuksen lukitus voidaan purkaa antamalla käyttäjälle uusi salasana tai PIN-koodi.   Esimerkiksi asiakastunnusten lukittuessa on mahdollista, että kirjastokortin numero on päätynyt vääriin käsiin ja asiakkaan tietoja yritetään anastaa tai aiheuttaa muuta vahinkoa. Tällaisissa tapauksissa asiakkaalle tulisi mieluummin antaa kokonaan uusi kirjastokortti ja PIN-koodi.

Vanhentuneilla virkailijatunnuksila kirjautuminen järjestelmään estetään. Tunnuksen voimassaoloajan jatkaminen Kohan liittymässä aktivoi tunnuksen jälleen takaisin käyttöön, salasana ei muutu.

Kaksivaiheinen tunnistautuminen tulee olla käytössä pääkäyttäjäoikeuksin varustetuilla tunnuksilla ja sen käyttö on suositeltavaa muillakin virkailijatunnuksilla.

## Tunnukset ja kirjautuminen

Virkailija- ja API-tunnuksia hallinnoivat pääsääntöisesti kimppojen pääkäyttäjät tai muut kimpan/kirjaston johdon valtuuttamat henkilöt. Koha-Suomi ei anna tunnuksia Koha-järjestelmiin, lukuunottamatta suoraan Koha-Suomen palveluksessa olevalle henkilökunnalle annettavia tunnuksia. Ennen tunnuksen luontia tulee olla selvillä miksi tunnus tarvitaan, kuka tarvitsee, mihin tunnusta tullaan käyttämään ja kuinka kauan sitä tarvitaan. Uusissa rajapinta-avauksissa tulee lisäksi aina konsultoida Koha-Suomea ennen tunnuksen antamista. Kimpan ja sen kuntien tietosuojaselosteiden läpikäynti ja päivitys voi myös olla tarpeen jos tunnuksia tehdään ulkopuolisille tahoille.

Virkailjatunnukset täytyy erottaa virkailijan lainaajatunnuksista. Lainaajatunnuksien kanssa ei ole kirjastoautomaatiosta johtuen mahdollista käyttää riittävän vahvoja salasanoja. Virkailijatunnusten salasanojen tulisi olla vähintään aakkosnumeerisia ja riittävän pitkiä, kyberturvallisuuskeskus suosittelee vähintään 15 merkkiä. Sama koskee myös automaattien käyttämiä SIP-tunnuksia.

Pääkäyttäjille kannattaa tehdä toinen matalammin käyttöoikeuksin varustettu tili perustyöskentelyyn. Pääkäyttäjätasoisin oikeuksin varustettua tiliä tulisi käyttää vain silloin kun sille on tarve.

Kohasta tulee aina ja ilman poikkeuksia kirjautua ulos jos virkailija poistuu koneen äärestä. Selain tai yksityisen selauksen ikkuna tulee sulkea Kohasta uloskirjautumisen jälkeen, tai vaihtoehtoisesti tyhjentää selaimen sivuhistoria ja evästeet. Tätä varten voi olla järkevää nostaa "Unohda" (engl. "Forget") nappi suoraan selaimen työkaluriville, josta se on helposti klikattavissa. Ohje tähän löytyy "täältä":https://support.mozilla.org/fi/kb/firefoxin-painikkeiden-tyokalupalkkien-muokkaaminen.

Kohan järjestelmäasetus 'Timeout' määrittää kuinka pitkän ajan kuluttua toimettomana ollut käyttäjä kirjataan ulos Kohasta. Asetuksen arvo kertoo ajan sekunteina. Suosittelemme timeout-ajaksi enintään puolta tuntia (1800 sekuntia). Lyhyempi timeout-aika on tietoturvan kannalta aina parempi.

Erillisen käyttäjätunnuksen käyttö kirjastokorttinumeron rinnalla ei ole suositeltavaa. Kaksi rinnakkaista tunnusta voi aiheuttaa sekaannuksia ja avata ylimääräisiä hyökkäysreittejä järjestelmään. Asiakaskirjautumisen tulisi aina tapahtua kirjastokortin numerolla ja siihen liitetyllä PIN-koodilla. Virkailijakirjautumisen taas tunnuksella ja vahvalla salasanalla. Nykyään käyttäjätunnus ja kirjastokortin numero lukitaan samaksi automaattisesti, mikä tarkoittaa, että erillistä käyttäjätunnusta (userid) ei voi käyttää.

Asiakkaiden varaustunnukseksi ei tulisi hyväksyä kirjautumiskelpoisia tunnuksia, esimerkiksi kirjastokortin numeroita. Varaustunnuksen ei ole tarkoitus avata pääsyä järjestelmään tai kirjaston palveluihin, vaan ainoastaan anonyymisti identifioida tietylle asiakkaalle menossa olevat varaukset noutohyllyssä.

## Käyttöoikeudet

Kullakin käyttäjällä tulisi olla ainoastaan juuri ne oikeudet, joita hänen työtehtäviensä hoitaminen edellyttää. Kimpan pääkäyttäjien täytyy huolehtia henkilöstön muuttuneiden työtehtävien aiheuttamista käyttöoikeuksien muutostarpeista Kohassa ja käyttöoikeuksien ja työtehtävien vastaavuus on hyvä kartoittaa koko henkilöstön laajuisesti säännöllisesti.

Erityisesti lokien katselu, asetusten muokkaus, uutisten julkaiseminen sekä tiedostojen lataaminen järjestelmään täytyy rajata ainoastaan niiden henkilöiden käyttöön, joilla on todellinen ja perusteltu tarve näille toiminnoille, esimerkiksi pääkäyttäjille. Huomionarvoisia, laajan pääsyn järjestelmään antavia oikeuksia ovat mm:

* management
* parameters_remaining_permissions
* batch_upload_patron_images
* stage_marc_import
* upload_general_files
* upload_local_cover_images
* upload_manage
* view_system_logs
* import_patron_data
* edit_news
* edit_quotes

Näiden kanssa on siis oltava erityisen tarkkana.

## Automaatit

Automaattien yhteys Koha-palvelimelle pitää salata. Ensisijainen ratkaisu tähän on SIP2oHTTPS (SIP2 over HTTPS) REST-endpoint. Vanhoja automaatteja varten voidaan tarvittaessa rakentaa salattuja tunneleita. Salaamaton liikennöinti SIP2-palvelimen ja automaattien välillä on ehdottomasti kielletty eikä ole teknisestikään mahdollista.

Lainausautomaateilla, omatoimijärjestelmissä ja Kohan itsepalvelulainauksessa tulisi kirjastoasiakkaiden oikeusturvan ja tietosuojan vuoksi käyttää PIN-koodin kyselyä.

## Miten toimia, jos huomaat tietoturvaan liittyvän ongelman

Jos huomaat tietoturvaan liittyvän ongelman, ole yhteydessä kimppasi pääkäyttäjään suojatusti (turvaposti, puhelu). Kimppojen pääkäyttäjät voivat laittaa Koha-Suomelle viestin ongelmasta turvapostilla osoitteeseen support(ät)koha-suomi.fi tai Matrixissa suojatussa huoneessa. Työasemien katoamista ja varkaustapauksia varten löytyy erillinen toimintaohje [Jos työasema varastetaan tai katoaa](/dokumentaatio/työasemavarkaus/)
