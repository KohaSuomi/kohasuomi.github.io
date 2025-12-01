# Jos virkailijatyöasema varastetaan tai katoaa

Tämä ohje kertoo mitä tehdä, jos kirjaston virkailijatyöasema varastetaan tai muuten katoaa. Toimintaohjeet on suunnattu ensisijassa loppukäyttäjille (kirjastoille ja niiden henkilökunnalle). Noudata ohjeita tarkasti estääksesi tilien väärinkäytön ja minimoidaksesi tietoturvariskit.

- Ota viipymättä yhteys kirjastokimpan pääkäyttäjään (yhteystiedot löyvät kimpoittain osoitteesta: https://github.com/KohaSuomi/Koha/wiki/Koha-yhteystiedot).
- Pääkäyttäjä ottaa yhteyttä Koha-Suomen päivystäjään.
- Riippuen katoamisesta kuluneesta ajasta voidaan tilin tunnuksia väliaikaisesti tai pysyvästi disabloida, tai joutua uusimaan tai perumaan.

1. Heti tehtävät
- Kirjaston virkailija: soita välittömästi kirjastokimpan pääkäyttäjälle ja kerro lyhyesti seuraavat tiedot, sikäli kun ne ovat tiedossa:
  - Kuka soittaa (nimi ja asema)
  - Milloin laite havaittiin kadonneeksi / varastetuksi (päivämäärä ja kellonaika)
  - Missä laite viimeksi nähtiin / oletettu tapahtumapaikka
  - Onko laitteella käytössä kunnan tietotekniikkapalveluiden etähallinta
  - Ovatko laitteen käyttäjäprofiilit paikallisia vai säilytetäänkö niitä kunnan palvelimilla
- Pääkäyttäjä: ilmoita välittömästi Koha-Suomen päivystäjälle ja toimita edellä mainitut tiedot. Päivystäjä eskaloi asian Koha-Suomen sisäisesti oikeille henkilöille.

2. Tarvittavat tiedot
- Käyttäjätilit jotka olivat kirjauduttuina laitteella tai joilla on kirjauduttu laitteella
- Onko laitteessa ollut tallennettuja sertifikaattitiedostoja (esim. .p12/.pfx) tai niiden salasanoja
- Onko laitteessa ollut tallennettuna Koha-tunnusten salasanoja selaimen salasananhallintaan tai salaamattomiin tiedostoihin
- Onko etähallintaratkaisua (voi mahdollistaa etäpyyhinnän)

3. Tekninen reagointi
- Laitteella olevien Koha-tunnusten käyttö tulee estää mahdollisimman pikaisesti. Tämä voidaan tehdä joko suoraan Kohan liittymästä tai se voidaan hoitaa päivystysasiana Koha-Suomessa, jos disabloitavia tunnuksia on suuri määrä.
- Selvitettävä millaisia oikeuksia laitteella käytetyillä Koha-tunnuksilla oli.
- Kunnan IT voi mahdollisesti suorittaa laitteen etäpyyhkimisen jos laitteen sijainti on tuntematon ja tiedonpaljastumisen riski on korkea.
- Suosittelemme ottamaan käyttöön kaksivaiheisen tunnistautumisen virkailijatunnuksille, jos mahdollista.

4. Salasanojen ja sertifikaattien käsittely
- Älä koskaan tallenna työaseman kovalevylle tai julkisille kansioille:
  - salasanoja selväkielisinä tiedostoina
  - sertifikaattitiedostoja (.p12/.pfx) tai niiden salasanoja
- Älä koskaan salli selaimen tallentaa salasanoja Koha-tunnuksille. Poista mahdollisesti tallennetut salasanat selaimista:
  - Chrome/Edge: Asetukset > Automaattinen täyttö > Salasanat > poista tallennetut
  - Firefox: Asetukset > Tietosuoja & suojaus > Tallennetut kirjautumistiedot > Poista
- Jos epäilet että salasanat tai sertifikaatit on tallennettu laitteelle, ilmoita tästä erikseen pääkäyttäjälle/päivystäjälle. TÄMÄ ON ERITTÄIN TÄRKEÄÄ!

5. Poliisi- ja lakisääteiset toimet
- Mikäli on syytä epäillä, että esimerkiksi Kohaan tallennetut henkilötiedot ovat voineet vaarantua, tee rikosilmoitus poliisille.
- Arvioi tietosuojaloukkaus: jos henkilötiedot ovat vaarantuneet, toimi organisaation tietosuojavastaavan ohjeiden mukaisesti ja tee ilmoitus valvontaviranomaiselle tarvittaessa (GDPR).
