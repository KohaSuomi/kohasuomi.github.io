---
title: 'IntranetUserJS'
permalink: /dokumentaatio/intranetuserjs/
redirect_from:
  - /theme-setup/
toc: true
---

Seuraavia koodinpätkiä voi laittaa IntranetUserJS-järjestelmäasetukseen.

HUOM! Koha-Suomen kirjastojen pääkäyttäjät: Kohaan tehdyn tietoturva-auditoinnin perusteella IntranetUserJS-järjestelmäasetukseen on lisätty ominaisuus, että asetuksen sisällöstä lasketaan tarkistussumma, joka tallennetaan koha-confiin. Asetukseen tallennetut JavaScriptit ajetaan vain, jos tarkistussumma täsmää. Jos tarkistussumma ei täsmää, Kohan käyttöliittymän toiminta keskeytetään, jotta asetuksesta ei saa ajettua mahdollista haittakoodia. Jos asetukseen muuttaa yhdenkin merkin, tarkistussumma muuttuu. Jos teet muutoksia IntranetUserJS-järjestelmäasetukseen, huolehdi ennakkoon, että joku kehittäjistä on päivittämässä samaan aikaan tarkistussumman koha-confiin.

Kun Kohan käyttöliittymän toiminta pysäytetään IntranetUserJS-järjestelmäasetuksen tarkistussumman vuoksi, tulee ilmoitus: KOHA IS STOPPED DUE TO CHECKSUM MISMATCH IN SYSTEM PREFERENCES. PLEASE CONTACT YOUR SYSTEM ADMINISTRATOR.

[Muutokseen liittyvä tiketti](https://tiketti.koha-suomi.fi/issues/4343)



## Lainaus

### Alt+p tulostaa kuitin

Tarpeellisuus: Korvattu _IntranetUserJS: Qslip keyboard shortcut_ -liitännäisellä <br />
Versio: 23.11

```
/// ALKU ///
// Alt+P tulostaa pikakuitin (tämän päivän lainat) lainaussivulla
$(document).ready(function(){
  if (window.location.pathname == '/cgi-bin/koha/circ/circulation.pl') {
    window.addEventListener("keydown", function (event) {
      if (event.altKey && event.key === "p") {
        window.open("/cgi-bin/koha/members/printslip.pl?borrowernumber=" + borrowernumber + "&amp;print=issueqslip", "printwindow");
      }
    });
  }
});
/// LOPPU ///
```

## Palautus

### "Poista käsin poistettujen varausten maksut" -täppä päälle

Tarpeellisuus: Korvattu _IntranetUserJS: Set defaults for Koha fields and checkboxes_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///

/* Laita raksi "Poista käsin poistettujen varausten maksut" -kohtaa palautuksessa. Tällä estetään noutamattoman varauksen maksun syntyminen, kun varaus noudettavissa oleva varaus poistetaan palautuksen kautta. Huom! Ei toimi, jos palautus tehdään muualla kuin Palautus-sivulla. */
$(document).ready(function () {
  $("#forgivemanualholdsexpire").attr('checked', true);
});

/// LOPPU ///
```

---

## Asiakkaan muokkausnäyttö


### Muu nimi (other name) -kentän piilottaminen määritellyiltä asiakastyypeiltä

Versio: 24.05

```
// Muu nimi (other name) -kentän piilottaminen määritellyiltä asiakastyypeiltä:
$(document).ready(function () {
    if ( window.location.pathname == '/cgi-bin/koha/members/memberentry.pl' ) {
        var categories = ["YHTEISO", "KAUKOLAINA", "AUTOM", "EITILASTO", "VIRKAILIJA", "API"];
        if ( ( window.location.search.includes('?op=add') && categories.some(cat => window.location.search.includes(cat)) ) || ( ( window.location.search.includes('?op=edit_form') || window.location.search.includes('?op=duplicate') ) && categories.some(cat => $('.patroncategory')[0].innerHTML.includes(cat)) ) ) {
            // Piilottaa li-elementin, jonka sisällä on label ja input
            $('#othernames').parent().hide();
        }
    }
});
/// LOPPU ///
```


### Piilota Perheen lainat -välilehti

Tarpeellisuus: Ei tarpeellinen, [muutettu CSS:ksi versiossa 23.11](https://koha-suomi.fi/dokumentaatio/intranetusercss/#piilota-perheen-lainat--v%C3%A4lilehti)<br />
Versio: 22.11


```
/// ALKU ///
/* Piilota Perheen lainat -välilehti */
$(document).ready(function() { $("#relatives-issues-tab").parent().hide(); });
/// LOPPU ///
```

### Henkilötunnuksen lisäys sotusiiloon ja syntymäajan asettaminen automaattisesti henkilötunnuksesta

Lisää asiakkaan muokkausnäytölle Henkilötunnus-kentän ja sen viennin sotusiiloon sekä asettaa automaattisesti syntymäajan henkilötunnuksen perusteella.

Tarpeellisuus: Muutettu osaksi Sotusiilo-liitännäistä versiossa 23.11 <br />
Versio: 22.11

```
/// ALKU ///
/// Lisätään asiakkaan lisäys/muokkausnäytölle hetun lisäysmahdollisuus. Rimpsu myös muodostaa syntymäaika-kenttään tiedon henkilötunnuksen perusteella. ///
$(document).ready(function() {
    $("#entryform #memberentry_identity ol").before('<ol><li><label>Lisää hetu:</label><input type="text" id="ssnvalue"></input><button onclick="addSSN(event)">Tallenna</button></li></ol><hr/>');
});
function addSSN(event) {
    event.preventDefault();
    $.ajax({
        url: "/api/v1/contrib/kohasuomi/ssn/add",
        type: "POST",
        dataType: "json",
        contentType: "application/json; charset=utf-8",
        data: JSON.stringify({
            token: 'yS390RiiReRhd2qXBmEIkD',
            ssn: $("#ssnvalue").val()
        }),
        success: function(result) {
            alert(result.msg);
            var entry = $("#ssnvalue").val().trim();
            var dateofbirth = ((entry.substr(6, 1) == "-" ? "19": "20") + entry.substr(4, 2) + "-" + entry.substr(2, 2) + "-" + entry.substr(0, 2));
            var fp = document.querySelector("#dateofbirth")._flatpickr;
            fp.setDate(dateofbirth);
            $("#patron_attr_5").val(result.ssnkey); //Tämä id on katsottava järjestelmäkohtaisesti
        },
        error: function(err) {
            var message = JSON.parse(err.responseText).message;
            if ($.isNumeric(message)) {
                if (window.confirm('Asiakas on jo olemassa! Paina OK siirtyäksesi tietoihin.')) {
                    window.open('/cgi-bin/koha/members/moremember.pl?borrowernumber=' + message, '_blank');
                }
            } else {
                alert(message);
            }
        }
    });
}
/// LOPPU ///
```


### Poista asiakkaan muokkausnäytöllä kentistä ylimääräiset välilyönnit

Näillä kahdella JS:llä voi poistaa asiakkaan muokkausnäytöllä ylimääräiset välilyönnit kentistä. Näytöllä on kahta eriä kenttätyyppiä, minkä vuoksi JS:kin on kaksi. Funktiot poistaa kentistä välilyönnit alusta ja lopusta sekä useammat peräkkäiset välilyönnit välistä.

Tarpeellisuus: Korvattu _IntranetUserJS: Remove excess spaces_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
/* poista asiakkaan muokkausnäytön kentistä välilyönnit alusta, lopusta ja useammat peräkkäiset välilyönnit välistä*/
$(document).ready(function() {
  $('body#pat_memberentrygen.pat input').blur(function() {
     var tmp = $(this).val();
     tmp = tmp.replace(/^ +/, '');
     tmp = tmp.replace(/ +$/, '');
     tmp = tmp.replace(/  */g, ' ');     
     $(this).val(tmp);
  });
});
/// LOPPU ///
```

```
/// ALKU ///
/* poista asiakkaan muokkausnäytön kentistä välilyönnit alusta, lopusta ja useammat peräkkäiset välilyönnit välistä*/
$(document).ready(function() {
  $('body#pat_memberentrygen.pat textarea').blur(function() {
     var tmp = $(this).val();
     tmp = tmp.replace(/^ +/, '');
     tmp = tmp.replace(/ +$/, '');
     tmp = tmp.replace(/  */g, ' ');     
     $(this).val(tmp);
  });
});
/// LOPPU ///
```


### Aseta syntymäpäiväkalenterin alasvetovalikon vuodet

Raja on 50 edellistä vuotta.

Tarpeellisuus: Ei tarpeellinen versiossa 22.11


```
/// ALKU ///
/* aseta syntymäpäivä-datepickerin dropdownin vuodet */
$(document).ready(function() {
  $("body#pat_memberentrygen.pat #dateofbirth").datepicker({yearRange: "c-50:c+1"});
});
/// LOPPU ///
```

### Kopioi matkapuhelinnumero SMS-tekstiviestinumerokenttään

Tämä on korvattu tietokannan triggerillä.

```
$(document).ready(function() {
  $("body#pat_memberentrygen.pat input#mobile").blur(function() {
    var v = $(this).val().trim();
    var e = $("input#SMSnumber");
    if (e) {
       e.val(v);
       e.change();
    }
  });
});
```

### Kopioidaan kirjastokortin numero käyttäjätunnus-kenttään

Tämä on korvattu tietokantatriggerillä.

Vaatii, että käyttäjän pitää klikata kirjastokortti-kentän ulkopuolelle (esim. tallentaa tiedot), jotta tieto kopioituu.

```
$(document).ready(function() {
  $("body#pat_memberentrygen.pat input#cardnumber").blur(function() {
    var v = $(this).val().trim();
    var e = $("input#userid");
    if (e) {
       e.val(v);
    }
  });
});
```

### Varaustunnuksen generointi

Skripti generoi HOLDID-asiakasmääreeseen anonyymin varaustunnisteen, joka on käytännössä UNIX-aikaleima.

Tarpeellisuus: Korvattu _IntranetUserJS: HoldID_ -liitännäisellä<br />
Versio: 23.11

```
//ALKU
// Varaustunnuksen automaattinen generointi. Kentän jälkeen lisätty kolme pistettä, josta muodostus tapahtuu. Uudelle asiakkaalle varaustunnus muodostuu automaattisesti kolmea pistettä painamatta.
// Tarkista oman tietokannan oikea payhdessätron_attr-arvo esim. selaimen Tarkista/Inspect element -toiminnolla.
$(document).ready(function(){
    if (window.location.pathname == '/cgi-bin/koha/members/memberentry.pl' && window.location.search.includes("?op=add&") || window.location.search.includes("?op=duplicate&")) {
      var unixepoch = Math.round( (new Date()).getTime() / 10 ).toString();
      var epochdashed = unixepoch.replace( /(....)/g, '$1-').replace(/-$/,'' );
      $('textarea#patron_attr_2').val(epochdashed);
      
	  $( '<a class="buttonDot" href="#" id="generate_holdid" title="Luo varaustunnus" style="vertical-align: top;"> ...</a>' ).insertAfter( "#patron_attr_2");
	  $("#generate_holdid").click(function(event) {
        event.preventDefault();
          unixepoch = Math.round( (new Date()).getTime() / 10 ).toString();
          epochdashed = unixepoch.replace( /(....)/g, '$1-').replace(/-$/,'' );
          $('textarea#patron_attr_2').val(epochdashed);
		  $("#patron_attr_2").trigger('blur');
      });
    }

      if (window.location.pathname == '/cgi-bin/koha/members/memberentry.pl' && window.location.search.includes("?op=modify")) {
	  $( '<a class="buttonDot" href="#" id="generate_holdid" title="Luo varaustunnus" style="vertical-align: top;"> ...</a>' ).insertAfter( "#patron_attr_2");
	  $("#generate_holdid").click(function(event) {
        event.preventDefault();
          unixepoch = Math.round( (new Date()).getTime() / 10 ).toString();
          epochdashed = unixepoch.replace( /(....)/g, '$1-').replace(/-$/,'' );
          $('textarea#patron_attr_2').val(epochdashed);
		  $("#patron_attr_2").trigger('blur');
      });
    }
});
//LOPPU
```


### Asiakasmääreen piilotus

Asiakasmääreen saa piilotettua muokkausnäytöllä seuraavalla rimpsulla. "patron_attr_1"-kohtaan voi vaihtaa tarvittaessa toisen numeron ykkösen sijalle. Numero kertoo, monesko määre on listalla.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: ?

```
/// ALKU ///
$( document ).ready(function() {
  $( '#pat_memberentrygen #memberentry_patron_attributes #patron_attr_1' ).parents( 'li' ).remove();
});
/// LOPPU ///
```

### Puhelinnumeron validointi ja viestitäppien poisto, jos puhelinnumero tai sähköpostiosoite puuttuu

Versioon 20.05 ja uudempaan. Tarkoitettu korvaamaan järjestelmäasetus ValidatePhoneNumber (kts. #4650).

Tässä on kaksi toiminnallisuutta yhdessä, koska ne ovat riippuvaisia toisistaan toiminnallisesti.

Lisäksi mukana on apuskripti puhelinnumeron tarkistus/viestitäppä -skriptille

Tämä apuskripti tarvitaan edellisen kaveriksi, jotta viestitäppien poisto onnistuu ensimmäisellä tallennuskerralla. [Liittyy tikettiin 538](https://github.com/KohaSuomi/Koha/issues/538).

Tarpeellisuus: Korvattu _IntranetUserJS: Validate mobile numbers and uncheck messaging preferences_ -liitännäisellä
Versio: 23.11

```
/// ALKU ///
/* Puhelinnumeron muodon tarkistus (suomalaiset numerot) ja email/sms-viestitäpät*/
// Add additional validation to member add/edit form
$(document).ready(function () {
  if (window.location.href.indexOf("members/memberentry.pl") > -1) {
    $('#SMSnumber').attr('disabled', 'disabled');
    $('.sms_number_help').text("Arvo kopioituu Matkapuhelin-kentästä tallennettaessa.");
    
   // Replace forms "Save" button 
   // (otherwise form is sent regardless validation checks made here) 
   var language = $(".currentlanguage").text();
   var save_text; 
   if(language == "Suomi"){
     save_text = "Tallenna";
   }else if(language == "Svenska"){
     save_text = "Spara";
   }else {
     save_text = "Save";
   }

  $('#pat_memberentrygen #saverecord').replaceWith('<button class="btn btn-primary" id="modified_saverecord"><i class="fa fa-save"></i> '+save_text+'</button>');

    var isvalid = 1;

    $('#phone').blur(function () {
      var error_mes = "";
      var phone = $('#phone').val();
      var phone_reg = /^((90[0-9]{3})?0|\+358)(?!(100|20(0|2(0|[2-3])|9[8-9])|300|600|700|708|75(00[0-3]|(1|2)\d{2}|30[0-2]|32[0-2]|75[0-2]|98[0-2])))(4|50|10[1-9]|20(1|2(1|[4-9])|[3-9])|29|30[1-9]|71|73|75(00[3-9]|30[3-9]|32[3-9]|53[3-9]|83[3-9])|2|3|5|6|8|9|1[3-9])(\d?){4,19}\d$/;

      if (phone && !phone_reg.test(phone)) {
        error_mes = error_mes + "\nPlease enter a valid phone number.\n";
        $('#phone').after('<label id="phone-error" class="error" for="phone">' + error_mes + '</label>');
        isvalid = 0;
      } else {
        isvalid = 1;
      }
    });

    $('#mobile').blur(function () {
      var error_mes = "";
      var mobile = $('#mobile').val();
      var mobile_reg = /^((90[0-9]{3})?0|\+358)(?!(100|20(0|2(0|[2-3])|9[8-9])|300|600|700|708|75(00[0-3]|(1|2)\d{2}|30[0-2]|32[0-2]|75[0-2]|98[0-2])))(4|50|10[1-9]|20(1|2(1|[4-9])|[3-9])|29|30[1-9]|71|73|75(00[3-9]|30[3-9]|32[3-9]|53[3-9]|83[3-9])|2|3|5|6|8|9|1[3-9])(\d?){4,19}\d$/;

      if (mobile && !mobile_reg.test(mobile)) {
        error_mes = error_mes + "\nPlease enter a valid mobile number.\n";
        $('#mobile').after('<label id="mobile-error" class="error" for="mobile">' + error_mes + '</label>');
        isvalid = 0;
      } else {
        isvalid = 1;
      }
    });

    $('#SMSnumber').blur(function () {
      var error_mes = "";
      var SMSnumber = $('#SMSnumber').val();
      var SMSnumber_reg = /^((90[0-9]{3})?0|\+358)(?!(100|20(0|2(0|[2-3])|9[8-9])|300|600|700|708|75(00[0-3]|(1|2)\d{2}|30[0-2]|32[0-2]|75[0-2]|98[0-2])))(4|50|10[1-9]|20(1|2(1|[4-9])|[3-9])|29|30[1-9]|71|73|75(00[3-9]|30[3-9]|32[3-9]|53[3-9]|83[3-9])|2|3|5|6|8|9|1[3-9])(\d?){4,19}\d$/;

      if (SMSnumber && !SMSnumber_reg.test(SMSnumber)) {
        error_mes = error_mes + "\nPlease enter a valid SMS number.\n";
        $('#SMSnumber').after('<label id="SMSnumber-error" class="error" for="SMSnumber">' + error_mes + '</label>');
        isvalid = 0;
      } else {
        isvalid = 1;
      }
    });

    $('#modified_saverecord').click(function (e) {
      var text = "";
      if (isvalid == 1) {
        //Vahvista viestitäppien poisto jos sähköposti/matkapuhelin puuttuu popupissa

        if (!$('#email').val()) {
          if ($('#email1').attr('checked') || $('#email2').attr('checked') || $('#email3').attr('checked') || $('#email4').attr('checked') || $('#email5').attr('checked') || $('#email6').attr('checked') || $('#email10').attr('checked')) {
            text = "Sähköpostiosoite puuttuu. Sähköposti-viestiasetukset poistetaan.\n";
            $('#email1').removeAttr('checked');
            $('#email1').attr('disabled', 'disabled');
            $('#email2').removeAttr('checked');
            $('#email2').attr('disabled', 'disabled');
            $('#email3').removeAttr('checked');
            $('#email3').attr('disabled', 'disabled');
            $('#email4').removeAttr('checked');
            $('#email4').attr('disabled', 'disabled');
            $('#email5').removeAttr('checked');
            $('#email5').attr('disabled', 'disabled');
            $('#email6').removeAttr('checked');
            $('#email6').attr('disabled', 'disabled');
            $('#email10').removeAttr('checked');
            $('#email10').attr('disabled', 'disabled');
          }
        }
        if (!$('#mobile').val()) {
          if ($('#sms1').attr('checked') || $('#sms4').attr('checked') || $('#sms10').attr('checked')) {
            text += "Matkapuhelinnumero puuttuu. Tekstiviesti-viestiasetukset poistetaan.";
            $('#sms1').removeAttr('checked');
            $('#sms1').attr('disabled', 'disabled');
            $('#sms4').removeAttr('checked');
            $('#sms4').attr('disabled', 'disabled');
            $('#sms10').removeAttr('checked');
            $('#sms10').attr('disabled', 'disabled');
          }
        }

        if (text.charAt(0)){
          alert(text);
        }
        
        $("#entryform").submit();
      }
    }
    );
  }
});
//LOPPU

///ALKU///
/* Tiketti 538 Lisää viestitäppiin checked-arvot jo ne laitettaessa, jolloin viestiasetusten tarkistus onnistuu ensimmäisellä asiakastietojen tallennuskerralla */
$(document).ready(function () {
    if (window.location.href.indexOf("members/memberentry.pl") > -1) {
var classA = Array.from(document.getElementsByClassName("pmp_sms"))
     ,classB = Array.from(document.getElementsByClassName("pmp_email"))
     ,result = Array.from(new Set(classA.concat(classB)));

for (var i = 0; i < result.length; i ++) {
      result[i].onclick = function(){
    var checkStatus = $(this).is(':checked');   

    if(checkStatus){
        $(this).attr('checked', 'checked');
    }
    else{
        $(this).removeAttr('checked');
    }
   };
  }
}});
///LOPPU///
```


### Ilmoitusten oletuskielivalinnaksi suomi

Kuitit tulostuvat sekakielisinä, jos käytössä on oletuspohja. Tämä skripti asettaa kielivalinnaksi suomen, jos valittuna on tallennettaessa oletus.

Tarpeellisuus: Korvattu _IntranetUserJS: Set defaults for Koha fields and checkboxes_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
//Asiakkaalle lähtevien ilmoitusten oletuskielivalinta suomeksi
$(document).ready(function () {
  if (window.location.href.indexOf("members/memberentry.pl") > -1) {
    var $notices_lang_select = document.querySelector('#lang');
    var selected = $notices_lang_select.value;
    if (selected == 'default') {
      $notices_lang_select.value = 'fi-FI';  
    }
  }
});
/// LOPPU ///
```

###  Kielikoodien järjestys tarkan haun valikossa

Aakkostaa ja priorisoi kielivalinnat tarkassa haussa

Tarpeellisuus: Korvattu _IntranetUserJS: Alphabetize/prioritize advanced search languages_ -liitännäisellä
Versio: 23.11

```
/// ALKU ///
//Kielten aakkostaminen ja priorisointi tarkassa haussa
function sortSelect(select, startAt) {
    if(typeof startAt === 'undefined') {
        startAt = 0;
    }
    var texts = [];
    for(var i = startAt; i < select.length; i++) {
        texts[i] = [
            select.options[i].text.toUpperCase(),
            select.options[i].text,
            select.options[i].value
        ].join('|');
    }
    texts.sort();
    texts.forEach(function(text, index) {
        var parts = text.split('|');
        select.options[startAt + index].text = parts[1];
        select.options[startAt + index].value = parts[2];
    });
}

$(document).ready(function () {
  if ((window.location.pathname == ("/cgi-bin/koha/catalogue/search.pl") && !window.location.search) || (window.location.href.indexOf("/catalogue/search.pl?advsearch=1&edit_search") > -1) || (window.location.href.indexOf("/catalogue/search.pl?do=Clear") > -1))  {
    var selected_lang_limit = $( "#language-limit option:selected" ).val();
    var selected_orig_lang_limit = $( "#language-original-limit option:selected" ).val();

    sortSelect(document.getElementById('language-limit'), 1);
    $('#language-limit').find('option[value="ln,rtrn:eng"]')
         .insertBefore($('#language-limit').find('option:eq(1)'));
    $('#language-limit').find('option[value="ln,rtrn:swe"]')
         .insertBefore($('#language-limit').find('option:eq(1)'));
    $('#language-limit').find('option[value="ln,rtrn:fin"]')
         .insertBefore($('#language-limit').find('option:eq(1)'));
    $("#language-limit").val(selected_lang_limit);
    
    sortSelect(document.getElementById('language-original-limit'), 1);
    $('#language-original-limit').find('option[value="language-original,rtrn:eng"]')
         .insertBefore($('#language-original-limit').find('option:eq(1)'));
    $('#language-original-limit').find('option[value="language-original,rtrn:swe"]')
         .insertBefore($('#language-original-limit').find('option:eq(1)'));
    $('#language-original-limit').find('option[value="language-original,rtrn:fin"]')
         .insertBefore($('#language-original-limit').find('option:eq(1)'));
    $('#language-original-limit').val(selected_orig_lang_limit);
  }
});
/// LOPPU ///
```

### Varaustunnus-asiakasmääreen siirto

Tällä skriptillä saa siirrettyä Varaustunnus-asiakasmääreen Asiakasidentiteetti-osioon sivun alkuun. Voit joutua kokeilemaan skriptille eri paikkoja IntranetUserJS:ssä, jotta se asettuu oikeaan kohtaan.

Tarpeellisuus: Korvattu _IntranetUserJS: HoldID_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
// Varaustunnus-asiakasmääreen siirto asiakkaan muokkausnäytöllä asiakkaan nimen alapuolelle. Muista tarkistaa patron_atrr_-arvot vastaamaan oman kimpan tietoja. Rimpsu pitää laittaa asetukseen ennen henkilötunnuksen lisäys -rimpsua, jotta määre asettuu oikeaan kohtaan näytöllä.
$(document).ready(function () {
  if (window.location.href.indexOf("members/memberentry.pl") > -1) {
    var holdidlabel = $('label[for="' + "patron_attr_2" + '"]');
    var clearbutton = holdidlabel.next().next().next();
    clearbutton.replaceWith( '<button type="button" class="fa fa-fw fa-trash fa-lg" style="color:green; border:none;">' );
    holdidlabel.next().next().next().on('click', function(e){
        holdidlabel.next().val('');
    });
    var li = holdidlabel.parent();
    $( "#identity_lgd" ).next().append(li);
  }
});

/// LOPPU ///
```

### Sotuavain-asiakasmääreen siirto

Tällä skriptillä saa siirrettyä Sotuavain-asiakasmääreen Asiakasidentiteetti-osioon sivun alkuun. Voit joutua kokeilemaan skriptille eri paikkoja IntranetUserJS:ssä, jotta se asettuu oikeaan kohtaan.

Tarpeellisuus: Vapaaehtoinen. Siirretty osaksi sotusiilo-liitännäistä versiossa 23.11.<br />
Versio: 22.11

```
/// ALKU ///
// Sotuavain-asiakasmääreen siirto
$(document).ready(function () {
  if (window.location.href.indexOf("members/memberentry.pl") > -1) {
    var sotuavainlabel = $('label[for="' + "patron_attr_6" + '"]');
    var clearbutton = sotuavainlabel.next().next().next();
    clearbutton.replaceWith( '<button type="button" class="fa fa-fw fa-trash fa-lg" style="color:green; border:none;">' );
    sotuavainlabel.next().next().next().on('click', function(e){
        sotuavainlabel.next().val('');
    });
    var li = sotuavainlabel.parent();
    var ssnfield = $( '#ssnvalue' );
    ssnfield.parent().append(li);
  }
});
/// LOPPU ///
```



### Asiakkaan osoitteenmuutospyyntö- täppä oletuksena hyväksy

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/// ALKU ///
// Laita Muutospyynnöt-sivulla oletuksena valinta Hyväksy-kohtaan.
$(document).ready(function () {
if (window.location.pathname == '/cgi-bin/koha/members/members-update.pl') 
$('input:radio[value="approve"]').attr('checked', true); 
});
/// LOPPU ///
```

### othername-kentän piilotus määritetyiltä asiakastyypeiltä

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

Tämä javascript-rimpsu piilottaa määritetyiltä asiakastyypeiltä othernames-kentän näkyviltä. Rimpsu on tehty OUTI-kirjastoille ja liittyy [tikettiin 956](https://github.com/KohaSuomi/Koha/issues/956).

```
///ALKU///

// Piilottaa 'Other names' kentän valituille asiakastyypeille (categorycode) muokkauslomakkeilla (add, modify, duplicate)
$(document).ready(function () {
if ( window.location.pathname == '/cgi-bin/koha/members/memberentry.pl' ) {
var categories = ["YHTEISO", "KAUKOLAINA", "AUTOM", "EITILASTO", "VIRKAILIJA", "API"];
if ( ( window.location.search.includes('?op=add') && categories.some(cat => window.location.search.includes(cat)) ) || ( ( window.location.search.includes('?op=modify') || window.location.search.includes('?op=duplicate') ) && categories.some(cat => $('.patroncategory')[0].innerHTML.includes(cat)) ) ) {
$('#othernames').attr('disabled', 'disabled');
// Piilottaa li-elementin, jonka sisällä on label ja input
$('#othernames').parent().hide();
}
}
});
///LOPPU///
```

### Käyttökieli-asiakasmääreen siirto asiakkaan identitetti -osioon sivun alkuun

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
///ALKU///
// Käyttökieli-asiakasmääreen siirto asiakkaan identitetti -osioon sivun alkuun
$(document).ready(function () {
  if (window.location.href.indexOf("members/memberentry.pl") > -1) {
    var holdidlabel = $('label[for="' + "patron_attr_6" + '"]');
    var clearbutton = holdidlabel.next().next().next();
    clearbutton.replaceWith( '<button type="button" class="fa fa-fw fa-trash fa-lg" style="color:green; border:none;">' );
    holdidlabel.next().next().next().on('click', function(e){
        holdidlabel.next().val('');
    });
    var li = holdidlabel.parent();
    $( "#identity_lgd" ).next().append(li);
  }
});
///LOPPU///
```

---

## Asiakkaan tiedot -näyttö

### Piilota viestin tekijän nimi Tiedot-näytöllä

Tarpeellisuus: Vapaaehtoinen <br />
Versio: 24.05

```
/// ALKU ///
/* Piilota viestin tekijän nimi asiakkaan Tiedot-näytöllä. Huom! Piilottaa vain virkailijaliittymässä näytettävän viestin tekijätiedon. */
$("#messages .circ-hlt a").remove();
$("#messages .circ-hlt").each(function( index ){
  var str = $(this).text().replace("(  )", "");
  $(this).text(str);
});
/// LOPPU ///
```

### PIN-koodi nelinumeroiseksi

Tällä muutetaan skriptissä mainituille asiakastyypeille salasanan generointi nelinumeroiseksi. Ilman tätä, asiakkaille tulee aakkosnumeerisia salasanoja.

Tarpeellisuus: Korvattu _IntranetUserJS: Generate PIN codes_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU  ///
/// Tällä muutetaan tässä mainituille asiakastyypeille salasanan generointi nelinumeroiseksi. Ilman tätä, asiakkaille tulee aakkosnumeerisia salasanoja ///

/* Generoi henkilöasiakkaalle PIN-koodi salasanaksi */
function generate_patron_password() {
    // generate a PIN
    var chars = '0123456789';
    var length = 4;
    var password = '';
    for (var i = 0; i < length; i++) {
        password += chars.charAt(Math.floor(Math.random() * chars.length));
    }
    return password;
}

$(document).ready(function () {
    if (window.location.href.indexOf("members/member-password.pl") > -1) {
        $("body").on('click', "#fillrandom", function (event) {
           event.stopImmediatePropagation();
             event.preventDefault();

            var password = '';
            var patron = $('.patroncategory').text();
             if ( (patron.indexOf("HENKILO") >= 0) || (patron.indexOf("LAPSI") >= 0) || (patron.indexOf("YHTEISO") >= 0) || (patron.indexOf("KOTIPALVEL") >= 0) || (patron.indexOf("KIRJASTO") >= 0) || (patron.indexOf("MUUKUINLAP") >= 0) ) {
                password = generate_patron_password();
                $("#newpassword").val(password);
                $("#newpassword").attr('type', 'text');
                $("#newpassword2").val(password);
                $("#newpassword2").attr('type', 'text');
                return;
            }
            else {
                var pattern_regex = /(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{3,}/;
                while (!pattern_regex.test(password)) {
                    password = generate_password();
                }
                $("#newpassword").val(password);
                $("#newpassword").attr('type', 'text');
                $("#newpassword2").val(password);
                $("#newpassword2").attr('type', 'text');
                return;
            }

        });
    }
});

/// LOPPU ///
```

### Noudettavissa olevat varaukset valikon taakse

Skripti siirtää noudettavissa olevat varaukset valikon taakse, jolloin ne eivät pidennä näyttöä. Jos noudettavia varauksia on paljon, voi näyttö venyä hyvinkin pitkäksi ja lainataulukkoa saa etsiä monen rullauksen päästä.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 24.05

```
/// ALKU ///
/// Siirretään asiakkaan lainaus- ja tiedot-sivuille odottavat varaukset valikon alle ///

$( document ).ready(function() {
    if ( window.location.href.indexOf("members/moremember.pl") > -1 || window.location.href.indexOf("circ/circulation.pl") > -1 ){
      var emo = $( '#holdswaiting' ).parent();
      $( '#holdswaiting' ).detach().appendTo( emo );
      $( '#holdswaiting > h4:nth-of-type(1)' ).attr("data-toggle","collapse");
      $( '#holdswaiting > h4:nth-of-type(1)' ).attr("data-target","#collapseOmat");
      $( '#holdswaiting > h4:nth-of-type(1)' ).addClass("collapsed");
      $( '#holdswaiting > h4:nth-of-type(1)' ).append(' <i class="fa fa-caret-down"></i>');
      $( '#holdswaiting > ul:nth-of-type(1)' ).attr("id","collapseOmat");
      $( '#holdswaiting > ul:nth-of-type(1)' ).addClass("collapse");
      $( '#holdswaiting > h4:nth-of-type(2)' ).attr("data-toggle","collapse");
      $( '#holdswaiting > h4:nth-of-type(2)' ).attr("data-target","#collapseMuut");
      $( '#holdswaiting > h4:nth-of-type(2)' ).addClass("collapsed");
      $( '#holdswaiting > h4:nth-of-type(2)' ).append(' <i class="fa fa-caret-down"></i>');
      $( '#holdswaiting > ul:nth-of-type(2)' ).attr("id","collapseMuut");
      $( '#holdswaiting > ul:nth-of-type(2)' ).addClass("collapse");
      $( '#holdswaiting > h4:nth-child(1)' ).click(function(){
        if ( $( '#holdswaiting > h4:nth-of-type(1) > i' ).hasClass('fa-caret-down') ){
          $( '#holdswaiting > h4:nth-of-type(1) > i' ).removeClass('fa-caret-down');
          $( '#holdswaiting > h4:nth-of-type(1) > i' ).addClass('fa-caret-up');
        }
        else if ( $( '#holdswaiting > h4:nth-of-type(1) > i' ).hasClass('fa-caret-up') ){
          $( '#holdswaiting > h4:nth-of-type(1) > i' ).removeClass('fa-caret-up');
          $( '#holdswaiting > h4:nth-of-type(1) > i' ).addClass('fa-caret-down');
        }
      });
      $( '#holdswaiting > h4:nth-of-type(2)' ).click(function(){
        if ( $( '#holdswaiting > h4:nth-of-type(2) > i' ).hasClass('fa-caret-down') ){
          $( '#holdswaiting > h4:nth-of-type(2) > i' ).removeClass('fa-caret-down');
          $( '#holdswaiting > h4:nth-of-type(2) > i' ).addClass('fa-caret-up');
        }
        else if ( $( '#holdswaiting > h4:nth-of-type(2) > i' ).hasClass('fa-caret-up') ){
          $( '#holdswaiting > h4:nth-of-type(2) > i' ).removeClass('fa-caret-up');
          $( '#holdswaiting > h4:nth-of-type(2) > i' ).addClass('fa-caret-down');
        }
      });
    }
});

/// LOPPU ///
```

### Lisää huolettava -monivalintanapin lisäys

Tällä skriptillä saa muutettua Lisää huollettava -napin valikoksi, josta voi valita, mitä asiakastyyppiä lisättävällä huollettavalla käytetään. Tämä on tarpeellinen lähinnä niissä kimpoissa, joissa lapsiasiakastyyppejä on useampi omatoimirajoitteiden vuoksi. Tarkista, että asiakastyyppien tunnukset ja kuvaukset vastaavat kimppasi tietoja.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/// ALKU ///
/* Lisää huollettava monivalintanappi. Asiakastyyppien tunnisteet pitää tarkistaa ja muuttaa tarvittaessa kimpassa käytettäviin. */
$(document).ready(function() {
  if ( !!document.getElementById("addchild") ){
    var editpatron_url = new URLSearchParams(document.getElementById("editpatron").href);
    var asiakasnumero = editpatron_url.get('borrowernumber');
    var kayttokieli = 'Suomi';

    var lapsiLinkki = "/cgi-bin/koha/members/memberentry.pl?op=add&categorycode=LAPSI&guarantor_id=" + asiakasnumero;
    var omatoimilapsiLinkki = "/cgi-bin/koha/members/memberentry.pl?op=add&categorycode=LAOMATOIMI&guarantor_id=" + asiakasnumero;
    var muuHuollettavaLinkki = "/cgi-bin/koha/members/memberentry.pl?op=add&categorycode=MUUHUOL&guarantor_id=" + asiakasnumero;
    var lisaaHuollettavaNappi = "<div class='btn-group'><button class='btn btn-default dropdown-toggle' data-toggle='dropdown'><i class='fa fa-plus'></i><span id='huollettavaKaannos'> Lisää huollettava.</span> <span class='caret'></span></button><ul class='dropdown-menu'><li><a href=" + lapsiLinkki + ">Lapsiasiakas, omatoimi kielletty</a></li><li><a href=" + omatoimilapsiLinkki + ">Lapsiasiakas, omatoimi sallittu</a></li><li><a href=" + muuHuollettavaLinkki + ">Huollettava, muu kuin lapsi</a></li></ul></div>";

    $( "#editpatron" ).after( lisaaHuollettavaNappi );
    $('#addchild').css('display','none');

    kayttokieli = document.getElementsByClassName('currentlanguage')[0].innerHTML;
    if (kayttokieli == 'Suomi') {
      $("#huollettavaKaannos").text(" Lisää huollettava");
    }
    else if (kayttokieli == 'Svenska') {
      $("#huollettavaKaannos").text(" Lägg till barn");
    }
    else if (kayttokieli == 'English') {
      $("#huollettavaKaannos").text(" Add child");
    }
  }    
});
/// LOPPU ///
```

### Kirjastokortin numero viivakoodina näkyviin Kirjastotiedot-osioon

Tällä IntranetUserJS-rimpsulla saa asiakkaan kirjastokortin numeron näkymään viivakoodina kirjastotiedot-osiossa. [Liittyy tikettiin Asiakkaan viivakoodin esittäminen asiakastietonäytöllä #671](https://github.com/KohaSuomi/Koha/issues/671).

Tämä on muutettu [JS-liitännäiseksi intranetjs-moremember-borrower-barcode](https://github.com/KohaSuomi/koha-plugin-intranetjs-moremember-borrower-barcode).

Versio: 22.11

```
$(document).ready(function () {
  if (window.location.pathname == '/cgi-bin/koha/members/moremember.pl') {
    cardnumber = document.getElementById('patron-cardnumber').childNodes[2].nodeValue.trim();
    barcodeurl = "/cgi-bin/koha/svc/barcode?barcode=" + cardnumber.toUpperCase() + "&notext=1";
    $('li#patron-cardnumber').append('<br><img src="' + barcodeurl + '">');
  }
});
```

### Palautusilmoitus-välilehden piilotus asiakkaan tiedoissa ja lainoissa

Versio: 24.05

```
// Palautusilmoitus-välilehden piilotus asiakkaan tiedoissa ja lainoissa
$(document).ready(function(){ 
  $("a#return-claims-tab").parent().hide();
});
/// LOPPU ///
```


## Maksut

### Ceepos-maksu -napin lisäys

Tämä skripti lisää maksun maksamissivulle Ceepos-maksu -napin, jolla saa vietyä maksun Ceepos-kassaliittymään.

Tarpeellisuus: Vapaaehtoinen (Ceepos-kassaa käyttäville tarpeellinen). Muutettu osaksi [Ceepos-liitännäistä](https://github.com/KohaSuomi/koha-plugin-ceepos-integration) versiossa 23.11<br />
Versio: 22.11

```
/// ALKU ///

/// Ceepos-maksu -napin lisäys ///
/// Napin taustavärinä ja reunavärinä keltainen? #ffc32b ///

$(document).ready(function() {
  let ceeposBranches = ['JOE_JOE'];
  if (ceeposBranches.includes($("#logged-in-info-full .logged-in-branch-code").text())) {
    $("#payfine .action, #payindivfine .action").find("input").after('<input type="button" id="CeeposMaksu" class="btn btn-primary" style="margin-left:3px;"  value="Ceepos-maksu"  onclick="setCeeposPayment($(this))"/>');
   if(localStorage.getItem('ceeposOffice')){
     $('#payment_type').val(localStorage.getItem('ceeposOffice'));
   }
  }
  $('#paycollect').hide();
  $("#circmessages a[href*='/cgi-bin/koha/members/paycollect.pl'").hide();
  $("#patron_messages a[href*='/cgi-bin/koha/members/paycollect.pl'").hide();
});
function setCeeposPayment(element) {
  var ceeposOffice = $('#payment_type').find(":selected").val();
  localStorage.setItem('ceeposOffice', ceeposOffice);
  	let payments;
  	let borrowernumber;
    if($("#payindivfine").find("#pay_individual").val() == 1) {
      borrowernumber = $("#payindivfine").find("#borrowernumber").val();
       payments = [{'borrowernumber': $("#payindivfine").find("#borrowernumber").val(), 'accountlines_id': $("#payindivfine").find("#accountlines_id").val(), 'description': $("#payindivfine").find("#description").val(), 'amountoutstanding': $("#payindivfine").find("#amountoutstanding").val(), 'payment_type': $("#payindivfine").find("#debit_type_code").val(), 'office': ceeposOffice}];
} else {
  	borrowernumber = $("#payfine").find("#borrowernumber").val();
  	payments = [{'borrowernumber': $("#payfine").find("#borrowernumber").val(), 'accountlines': $("#payfine").find("#selected_accts").val(), 'amountoutstanding': $("#payfine").find("#collected").val(), 'office': ceeposOffice}];
}
    $.ajax({
     url: "/api/v1/contrib/kohasuomi/payments/ceepos", 
     type: "POST",
     dataType: "json",
     contentType: "application/json; charset=utf-8",
     data: JSON.stringify(payments),
     beforeSend: function() {
        $("#CeeposMaksu").attr("disabled", true);
        alert("Maksu lähetetty, käsittele kassassa!");
     },
     success: function (result) {
         location.href = '/cgi-bin/koha/members/boraccount.pl?borrowernumber='+borrowernumber;
      },
      error: function (xhr, status, error) {
          $("#CeeposMaksu").attr("disabled", false);
          alert(JSON.parse(xhr.responseText).error);
      }
   });
}

///LOPPU ///
```

---

## Tarkka haku

### Aineistolajirajauksen tyhjennys

Tarpeellisuus: Vapaaehtoinen<br />
Versio: ?

```
/* Aineistolajirajauksen tyhjennys tarkassa haussa */
function poista_itype_valinnat() {
 $('body#catalog_advsearch #advsearch-itemtypes input[id^="itypephr"]').each(function() { $(this).prop('checked', false)});
}
$(document).ready(function() {
  $('<a onclick="poista_itype_valinnat(); return false;" href="#">Tyhjennä</a>').insertAfter('body#catalog_advsearch #advsearch-itemtypes h4:first-of-type');
});
```

### Aseta hakukenttien oletukseksi nimeke, tekijä, ja sanahaku

Tiketti #494. Valikkojen oletus on sanahaku, joten kolmannen arvoa ei tarvitse erikseen asettaa.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/// ALKU ///

/* Tarkka-haku ja Sanahaku-oletustermit korvataan Nimeke, Tekijä, Asiasana */
$(document).ready(function() {
  var elems = $("body#catalog_advsearch select[name='idx']");
  elems.eq(0).val('ti');
  elems.eq(1).val('au');
  elems.eq(2).val('su');
});

/// LOPPU ///
```

Vaihtoehtoinen versio, jossa toimii kenttien pakotus myös, kun palataan Tarkkaan hakuun Muokkaa hakua -napista hakutuloksista.

Lisätty 9.4.2024
Tekijä: Mikko Liimatainen
Versio 23.11

```
// Tarkan haun Sanahaku-oletustermit korvataan Nimeke, Tekijä, Asiasana sivulla /cgi-bin/koha/catalogue/search.pl
$(document).ready(function() {
  let params = (new URL(document.location)).searchParams;
  let edit = params.get("edit_search");
  if (window.location.pathname == '/cgi-bin/koha/catalogue/search.pl' && !edit) {
    var elems = $("body#catalog_advsearch select[name='idx']");
    elems.eq(0).val('ti');
    elems.eq(1).val('au');
    elems.eq(2).val('su');
  }
});
//LOPPU
```

### Tarkan haun aineistotyyppivalintojen tyhjennys sivulla /cgi-bin/koha/catalogue/search.pl 

Versio: 24.05

```
// Tarkan haun aineistotyyppivalintojen tyhjennys sivulla /cgi-bin/koha/catalogue/search.pl 
if ($('body#catalog_advsearch').length){ 
  function poista_mtype_valinnat() {
    $('body#catalog_advsearch #advsearch-tab-mtype_panel input[id^="mtype"]').each(function() { $(this).prop('checked', false);});
  }
  $(document).ready(function() {
    $('<a id="aineistotyyppi_tyhjennys" onclick="poista_mtype_valinnat(); return false;" href="#">Tyhjennä</a>').insertAfter('body#catalog_advsearch #advsearch-tab-mtype_panel h4:first-of-type');
  });
}
//LOPPU
```

### Tietueen niteet välilehdellä tehtävien muokkausten esto. /cgi-bin/koha/catalogue/moredetail.pl

Versio: 24.05

```
// Tietueen niteet välilehdellä tehtävien muokkausten esto. /cgi-bin/koha/catalogue/moredetail.pl
$(document).ready(function() {
  if ( $("body#catalog_moredetail.catalog").length ){
	$("select[name='itemlost']").parent().parent().hide();
	$("select[name='damaged']").parent().parent().hide();
    $("select#exclude_from_local_holds_priority").parent().parent().parent().parent().parent().hide();
	$("textarea[name='itemnotes']").prop("disabled", true);
	$("textarea[name='itemnotes_nonpublic']").prop("disabled", true);
	$("input[type='submit'][value='Päivitä']").hide();
    $("input[type='submit'][value='Update']").hide();
    $("input[type='submit'][value='Uppdatering']").hide();
  }
});
//LOPPU
```

### Linkki Finna-näkymään

Tämä lisää tietueen perustiedot-näytölle valikkoriville viimeiseksi Avaa Finnassa -nappulan, joka vie oman kimpan Finnaan saman teoksen tietoihin.

Tarpeellisuus: Korvattu _IntranetUserJS: Add links to record in Finna_ -liitännäisellä <br />
Versio: 23.11

```
 /// ALKU ///
/// Lisää tietueen perustiedot-näytölle valikkoriville loppuun Avaa Finnassa -nappula. Muista vaihtaa osoitteisiin oman kimpan tunnisteet OUTIn tunnisteiden sijaan. ///

$( document ).ready(function() {
if (window.location.pathname == '/cgi-bin/koha/catalogue/detail.pl') {
  		var linktext = 'Avaa Finnassa';
        if( $( '#changelanguage .currentlanguage' ).text() == 'English' ) {
        	linktext = 'Open in Finna';
        } else if ( $( '#changelanguage .currentlanguage' ).text() == 'Svenska' ) {
        	linktext = 'Öppna i Finna';
        }
        var params = new URLSearchParams(window.location.search);
        var biblionumber = parseInt(params.get("biblionumber"));
  		$( '#catalog_detail #toolbar' ).append( '<div class="btn-group"> <a href="https://outi.finna.fi/Record/outi.' + biblionumber + '" class="btn btn-default" target="_blank"><i class="fa fa-external-link"></i> ' + linktext + '</a></div>' );
}
});

/// LOPPU ///
```

### Koriin linkit Finnaan jokaisesta teoksesta

Tämä lisää Koriin jokaiseen teokseen linkin myös Finnaan samaan teokseen. Muista vaihtaa Siilinjärven tietojen tilalle oikea osoite Finnaan sekä tietuetunniste ennen viimeistä pistettä osoitteessa.

Tarpeellisuus: Suositeltava<br />
Versio: 23.11

```
/// ALKU ///
// Finna-verkkokirjastolinkkien lisääminen ostoskoriin
$(document).ready(function () {
  if ( window.location.pathname == '/cgi-bin/koha/basket/basket.pl' ) {
    
    // Syötä tähän oman kimpan Finna-osoite
    var finnaurl = 'https://outi.finna.fi/Record/outi';

    var linkbase = '<a class="btn btn-default" style="margin:0 5px 5px 0;" target="_blank" href="' + finnaurl + '.';
    
    // Kielivalinta
    var linktext = 'Avaa Finnassa';
    var hostlinktext = 'Avaa emokohde Finnassa';
    if ( document.documentElement.lang.toLowerCase() === "en" ) {
      linktext = 'Open in Finna';
      hostlinktext = 'Open host record in Finna';
    } else if ( document.documentElement.lang.toLowerCase() === "sv-se" ) {
      linktext = 'Öppna i Finna';
      hostlinktext = 'Öppna huvudobjekt i Finna';
    }

    // Linkin muodostaminen
    $("td:has(a.title)").each(function() {
      if ( $(this).find('a.title').length > 1 ) {    
        var child_bib = $(this).find('a.title').eq(0).attr('href').replace('/cgi-bin/koha/catalogue/detail.pl?biblionumber=','');
        var host_bib = $(this).find('a.title').eq(1).attr('href').replace('/cgi-bin/koha/catalogue/detail.pl?biblionumber=',''); 
        var finnalinks = '<p>' + linkbase + child_bib + '"><i class="fa fa-external-link"></i> ' + linktext + '</a>' + linkbase + host_bib + '"><i class="fa fa-external-link"></i> ' + hostlinktext + '</a></p>';
        $(this).append(finnalinks);
      } else {
        var bib = $(this).find('a.title').eq(0).attr('href').replace('/cgi-bin/koha/catalogue/detail.pl?biblionumber=','');
        var finnalink = '<p>' + linkbase + bib + '"><i class="fa fa-external-link"></i> ' + linktext + '</a></p>';
        $(this).append(finnalink); 
      }
    });
  }
});
/// LOPPU ///
```

### Indeksointityöryhmän tekemät tiedonhaun mukautukset

Indeksointityöryhmä ideoi mukautuksia tiedonhakun hakusivulle. Alla siitä syntyneet muutokset.

Tarpeellisuus: Korvattu _IntranetUserJS: Changes to search page_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
/* Näillä rimpsuilla tehdään tiedonhakuun Indeksointi-työryhmän päättämät muutokset. Asetetaan otsikot eri kielillä aineistotyyppi-, hyllytarkenne- ja ikärajavälilehdille tiedonhaussa. Lisätään alasvetovalikoihin YKL, UDK, Päivittyvä julkaisu ja Kausijulkaisu */
$(document).ready(function() {

  if ( $('html').attr('lang') == 'fi-FI') {
    $("a#advsearch-tab-mtype-tab").text("Aineistotyyppi"); /* MTYPE auktorisoituarvo tarkassa haussa */
    $("a#advsearch-tab-subloc-tab").text("Hyllytarkenne"); /* SUBLOC auktorisoituarvo tarkassa haussa */
    $("a#advsearch-tab-agelevel-tab").text("Ikärajat"); /* AGELEVEL auktorisoituarvo tarkassa haussa */
    $("a#advsearch-tab-bib-level-tab").text("Emokohde/Osakohde"); /* bib-level auktorisoituarvo tarkassa haussa */
    $("#searchterms .advsearch").append(new Option('YKL-luokitus', 'other-classification')); /* Lisää uuden valinnan YKL-luokitus */
    $("#searchterms .advsearch").append(new Option('UDK-luokitus', 'udc-classification')); /* Lisää uuden valinnan UDK-luokitus */
    $("#subtype select option[value='mus:i'").parent().append(new Option('Päivittyvä julkaisu', 'bib-level:i')); /*Lisää lisärajoitukset valikkoon uuden arvon */
    $("#subtype select option[value='mus:i'").parent().append(new Option('Kausijulkaisu', 'bib-level:s')); /*Lisää lisärajoitukset valikkoon uuden arvon */
  }
  else if ( $('html').attr('lang') == 'sv-SE') {
    $("a#advsearch-tab-mtype-tab").text("Materialtyp");
    $("a#advsearch-tab-subloc-tab").text("Underplats");
    $("a#advsearch-tab-agelevel-tab").text("Åldersgränser");
    $("a#advsearch-tab-bib-level-tab").text("Huvudobjekt/Delobjekt");
    $("#searchterms .advsearch").append(new Option('YKL-klassification', 'other-classification'));
    $("#searchterms .advsearch").append(new Option('UDC-klassification', 'udc-classification'));
    $("#subtype select option[value='mus:i'").parent().append(new Option('Publikation som uppdateras', 'bib-level:i'));
    $("#subtype select option[value='mus:i'").parent().append(new Option('Seriell publikation', 'bib-level:s'));
  }
  else if ( $('html').attr('lang') == 'en') {
    $("a#advsearch-tab-mtype-tab").text("Material type");
    $("a#advsearch-tab-subloc-tab").text("Sub location"); 
    $("a#advsearch-tab-agelevel-tab").text("Age levels");
    $("a#advsearch-tab-bib-level-tab").text("Child/monographic record");
    $("#searchterms .advsearch").append(new Option('Other classification', 'other-classification'));
    $("#searchterms .advsearch").append(new Option('UDC classification', 'udc-classification'));
    $("#subtype select option[value='mus:i'").parent().append(new Option('Integrating resource', 'bib-level:i'));
    $("#subtype select option[value='mus:i'").parent().append(new Option('Serial', 'bib-level:s'));
  }
 });
/// LOPPU ///
```

---

## Luettelointi, niteiden muokkaus ja kausijulkaisut


### Poistetaan ylimääräiset välilyönnit niteen muokkausnäytöllä

Tällä poistetaan ylimääräiset välilyönnit kentistä niteen muokkausnäytöllä. Välilyönnit poistetaan alusta, lopusta ja useammat peräkkäiset välilyönnit välistä.

Tarpeellisuus: Korvattu _IntranetUserJS: Remove excess spaces_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
/* Poista niteen muokkausnäytön kentistä välilyönnit alusta, lopusta ja useammat peräkkäiset välilyönnit välistä*/
$(document).ready(function() {
  $('body#cat_additem.cat input').blur(function() {
     var tmp = $(this).val();
     tmp = tmp.replace(/^ +/, '');
     tmp = tmp.replace(/ +$/, '');
     tmp = tmp.replace(/  */g, ' ');
     $(this).val(tmp);
  });
});
/// LOPPU ///
```

### Poistetaan ylimääräiset välilyönnit kausijulkaisujen vastaantotossa

Skripti poistaa ylimääräiset välilyönnit sekä tarkistaa, että sarjanumero on muodossa "vuosi : numero". Jos vuoden jälkeen puuttuu välilyönti, käytännössä se lisätään sinne. Tarkistus tehdään kaikkiin nidekenttiin, mutta korjaus ei "tartu", jos kentän alussa ei ole vuosinumeroa.

Tarpeellisuus: Korvattu _IntranetUserJS: Remove excess spaces_ -liitännäisellä<br />
Versio: 23.11

```
//// ALKU ///
/* Poista kausijulkaisun vastaanottonäytön kentistä välilyönnit alusta, lopusta ja useammat peräkkäiset välilyönnit välistä*/
$(document).ready(function() {
  $('body#ser_serials-edit.ser input').blur(function() {
     var tmp = $(this).val();
     tmp = tmp.replace(/^ +/, '');
     tmp = tmp.replace(/ +$/, '');
     tmp = tmp.replace(/  */g, ' ');
     tmp = tmp.replace(/(^[1-2][0-9]{3}) *: */, '$1 : ');
     $(this).val(tmp);
  });
});
/// LOPPU ///
```

### Poistetaan ylimääräiset välilyönnit hankinnassa

Tarpeellisuus: Korvattu _IntranetUserJS: Remove excess spaces_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
/* Poista hankinnassa uuden tilauksen niteen muokkausnäytön kentistä välilyönnit alusta, lopusta ja useammat peräkkäiset välilyönnit välistä */
/* Tämä ei toimi? */
$(document).ready(function() {
  $('body#acq_neworderempty.acq').on("blur", "input", function() {
     var tmp = $(this).val();
     tmp = tmp.replace(/^ +/, '');
     tmp = tmp.replace(/ +$/, '');
     tmp = tmp.replace(/  */g, ' ');
     $(this).val(tmp);
  });
});
/// LOPPU ///

/// ALKU ///
/* Poista hankinnassa uuden tilauksen niteen muokkausnäytön kentistä välilyönnit alusta, lopusta ja useammat peräkkäiset välilyönnit välistä */ 
/* Tämä ei toimi? */
$(document).ready(function() {
  $('body#acq_neworderempty.acq').on("blur", "textarea", function() {
     var tmp = $(this).val();
     tmp = tmp.replace(/^ +/, '');
     tmp = tmp.replace(/ +$/, '');
     tmp = tmp.replace(/  */g, ' ');
     $(this).val(tmp);
  });
});
/// LOPPU ///
```

### Niteiden eräpoistossa täppä kohtaan "Poista tietueet.."

Skripti laittaa niteiden eräpoistossa valmiiksi täpän kohtaan "Poista tietueet, jos kaikki niteet poistettu". Näin todennäköisemmin tietokantaan ei jää roikkumaan niteettömiä tietueita.

Tarpeellisuus: Korvattu _IntranetUserJS: Set defaults for Koha fields and checkboxes_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
/* Laita niteiden eräpoistossa täppä kohtaan "Poista tietueet, jos kaikki niteet poistettu". Tällä varmistetaan, että tietokantaan ei jää niteettömiä tietueita. */
$(document).ready(function () {
$("#del_records").attr('checked', true);
});
/// LOPPU ///
```

### Niteen lisäys tarratulostusjonoon

Näillä skripteillä lisätään niteen muokkausnäytölle sekä teoksen perustiedot-näytölle mahdollisuus lisätä nide tarratulostusjonoon.

Tarpeellisuus: Siirretty osaksi tarratulostusliitännäistä versiossa 24.05 />
Versio: 23.11

```
/// ALKU ///
/// Niteiden lisäys tarratulostusjonoon. Ilman näitä niteitä ei saa vietyä niteiden muokkauksesta ja perustiedot-näytöltä omaan tulostusjonoon. ///

$(document).ready(function() {
    $(".print_label").after('<li><a href="#" onclick="setPrintQueue($(this))">Tulostusjonoon</a></li>');
  $("#addnewitem").after('<input type="button" style="margin-left:3px;" value="Tulostusjonoon" onclick="setPrintQueue($(this))"/>');
});

function setPrintQueue(element) {
  let searchParams = new URLSearchParams(element.parent().parent().find(".print_label a").attr("href"));
  let itemnumber = element.parent().find('input[name="itemnumber"]').val();
  let number = itemnumber ? itemnumber : searchParams.get('number_list');
  $.ajax({
   url: "/api/v1/contrib/kohasuomi/labels/print/queue", 
   type: "POST",
   async: false,
   dataType: "json",
   contentType: "application/json; charset=utf-8",
   data: JSON.stringify({ itemnumber: number, printed: 0 }),
   success: function (result) {
       alert("Nide lisätty jonoon!");
    },
    error: function (err) {
    	alert("Lisäys epäonnistui!");
    }
 });
}

/* Niteiden lisätys tarratulostustyökaluun perustiedot-näytöltä */
$(document).ready(function() {
    $("#holdings .itemselection_action_modify, #otherholdings .itemselection_action_modify").after(' <a href="#" class="itemselection_action_print" onclick="addItemsToPrintQueue(event, $(this))"><i class="fa fa-print"></i> Lisää valitut niteet tulostusjonoon</a>');
});
function addItemsToPrintQueue(e, element) {
    e.preventDefault();
    var requests = [];
    $("input[name='itemnumber'][type='checkbox']:visible:checked", 'table.items_table').each(function() {
        var itemnumber = $(this).val();
        requests.push($.ajax({
            url: "/api/v1/contrib/kohasuomi/labels/print/queue",
            type: "POST",
            async: false,
            datatype: "json",
            contentType: "application/json; charset=utf-8",
            data: JSON.stringify({ itemnumber: itemnumber, printed: 0 }),
            error: function (err) {
                console.error( `Niteen nro. ${itemnumber} lisäys tulostusjonoon epäonnistui.` );
            }
        }));
    });
    window.onbeforeunload = function () {
        if ( requests.length ) {
            return "";
        }
    };
    $('.itemselection_action_print').replaceWith(`<a class="itemselection_action_print disabled" style="cursor: not-allowed;"><i class="fa fa-print"></i> Lisätään ${requests.length} nide${requests.length == 1 ? "" : "ttä"} tulostusjonoon...</a>`);
    $.when.apply($, requests).done(function () {
        alert( `${requests.length} nide${requests.length == 1 ? "" : "ttä"} lisätty tulostusjonoon.` );
    }).fail(function () {
        alert( "Niteiden lisäys tulostusjonoon keskeytyi. Tarkista tulostusjono." );
    }).always(function () {
        $('.itemselection_action_print').replaceWith('<a href="#" class="itemselection_action_print" onclick="addItemsToPrintQueue(event, $(this))"><i class="fa fa-print"></i> Lisää valitut niteet tulostusjonoon</a>');
        requests = [];
    });
}

/// LOPPU ///
```

### Nidelistaus sivun loppuun niteen muokkauksessa

Tällä skriptillä saa siirrettyä niteen muokkauksessa nidelistauksen muokattavana olevan niten tietojen alapuolelle, eikä muokkaukseen mennessä tarvitse ensin kelata mahdollisesti kymmenien niteiden ohi.

Tarpeellisuus: Vapaaehtoinen<br />
Versio: 23.11

```
/// ALKU ///
/* Niteen muokkauksessa nidelistan siirto niteen muokkauksen alapuolelle */
$( document ).ready(function() {
  if (window.location.pathname == '/cgi-bin/koha/cataloguing/additem.pl') {
    $( '#cat_additem #cataloguing_additem_itemlist' ).after( $( '#cat_additem #cataloguing_additem_itemlist #itemst_wrapper' ).parents( 'div' ).html() );
    $( '#cat_additem #cataloguing_additem_itemlist #itemst_wrapper' ).parent( 'div' ).hide();
    $( '#cat_additem #cataloguing_additem_itemlist' ).prepend( $( '#cat_additem #cataloguing_additem_itemlist>.row' ) );
    $(window).scrollTop(0);
  }
});
/// LOPPU ///
```

### Z39.50-hakuikkuna suuremmaksi

Tällä skriptillä saa Z39.50-hakuikkunan suuremmaksi.

Tarpeellisuus: Vapaaehtoinen, ei enää välttämätön versiossa 24.05<br />
Versio: 23.11

```
/// ALKU ///

/* Muuta Z39.50-hakuikkunan koko suuremmaksi. Ikkunan koko on turhan pieni hakutuloksille. */
//Cataloging > Z39.50/SRU pop-up
 //BEGIN Resize Z39.50 window
  if (document.location.href.indexOf('z3950_search.pl')>-1) window.resizeTo((screen.width * 0.9), (screen.height * 0.9)), window.moveTo(0, 0);
  $(window).on('load resize', function(){
   $('#cat_z3950_search .col-xs-6 .rows, #cat_z3950_search #z3950_search_targets').height($(this).height() * 0.75);
   $('#cat_z3950_search .col-xs-6 .rows').css('overflow-y', 'scroll');
  });
//END

/// LOPPU ///
```

---

## Yleiset

### Piilota IntranetJS-pluginit Työkalut-sivulta työkaluliitännäisten listasta

Rimpsulla voi piilottaa Työkalut-sivulta sellaiset liitännäiset, joiden nimessä mainitaan IntranetUserJS-termi.

Tarpeellisuus: Suositeltava<br />
Versio 24.05

```
/// Piilota IntranetJS-pluginit työkalut-näkymästä työkaluliitännäisten listasta 
$(document).ready(function () {
  if (window.location.href.indexOf("tools/tools-home.pl") > -1) {
    $('span:contains("IntranetUserJS")').closest('.plugin_link').hide();
}});
```

### Estä näytön viertystä jumimasta

Kaikkien kannattaa lisätä tämä, jotta vieritys toimii oikein kaikilla näytöillä (eri kokoisilla), eikä jumitu kesken näytön vierityksen. Liittyy [tikettiin #106](https://github.com/KohaSuomi/Koha-24.05/issues/106).

Tarpeellisuus: Suositeltava<br />
Versio 24.05

```
/// ALKU  ///
/* Lisää huollettava monivalintanappi */
$(document).ready(function() {
  if ( !!document.getElementById("addchild") ){
    var editpatron_url = new URLSearchParams(document.getElementById("editpatron").href);
    var asiakasnumero = editpatron_url.get('borrowernumber');
    var kayttokieli = 'Suomi';

    var lapsiLinkki = "/cgi-bin/koha/members/memberentry.pl?op=add_form&categorycode=LAPSI&guarantor_id=" + asiakasnumero;
    var omatoimilapsiLinkki = "/cgi-bin/koha/members/memberentry.pl?op=add_form&categorycode=LAOMATOIMI&guarantor_id=" + asiakasnumero;
    var muuHuollettavaLinkki = "/cgi-bin/koha/members/memberentry.pl?op=add_form&categorycode=HUOLLETTAV&guarantor_id=" + asiakasnumero;
    var lisaaHuollettavaNappi = "<div class='btn-group'><button class='btn btn-default dropdown-toggle' data-toggle='dropdown'><i class='fa fa-plus'></i><span id='huollettavaKaannos'> Lisää huollettava.</span> <span class='caret'></span></button><ul class='dropdown-menu'><li><a href=" + lapsiLinkki + ">Lapsi</a></li><li><a href=" + omatoimilapsiLinkki + ">Lapsi, omatoimi sallittu</a></li><li><a href=" + muuHuollettavaLinkki + ">Huollettava, muu kuin lapsi</a></li></ul></div>";


    $( "#editpatron" ).after( lisaaHuollettavaNappi );
    $('#addchild').css('display','none');

    kayttokieli = document.getElementsByClassName('currentlanguage')[0].innerHTML;
    if (kayttokieli == 'Suomi') {
      $("#huollettavaKaannos").text(" Lisää huollettava");
    }
    else if (kayttokieli == 'Svenska') {
      $("#huollettavaKaannos").text(" Lägg till barn");
    }
    else if (kayttokieli == 'English') {
      $("#huollettavaKaannos").text(" Add child");
    }
  }    
});
```
### Piilota Uusinta-välilehti yläosan hakukentästä

Kohan uusinta-toiminnallisuus ei noudata laina- ja maksusääntöjä ja antaa uusia, vaikka teokseen kohdistuu varaus tai uusintakerrat ovat tulleet jo täyteen.

Tarpeellisuus: Ei tarpeen, [muutettu CSS:ksi versiossa 23.11](https://koha-suomi.fi/dokumentaatio/intranetusercss/#piilota-uusinta-nappi)<br />
Versio: 22.11

```
/// ALKU ///
$(document).ready(function () {
  $( "li[aria-controls='renew_search']" ).hide();
});
/// LOPPU ///
```

### Asiakastietojen piilotus Vastaanotettavat kuljetukset -raportilta

Vastaanotettat kuljetukset -raportilla näytetään asiakastietoja, jos kuljetettavaan niteeseen liittyy varaus. Tällä skriptillä asiakastiedot korvataan kuittaus-merkillä.

Tarpeellisuus: Korvattu _IntranetUserJS: Transfers to receive patron info to checkmark_ -liitännäisellä<br />
Versio: 23.11

```
/// ALKU ///
// Muuttaa vastaanotettavien kuljetusten varaustietokentän (transferstoreceive) muotoon kyllä/ei
$(document).ready(function () {
  if ( window.location.pathname == '/cgi-bin/koha/circ/transferstoreceive.pl' ) {

    $("th:contains('On hold for'), th:contains('Reserverad för')").append(" patron");

    $("td > p").filter(function() {
      // Matches exact string   
      return $(this).text() === "None" || $(this).text() === "Ei mitään";
    }).empty();

    $("td:has(a[href*='/cgi-bin/koha/members/moremember.pl?borrowernumber='])").addClass('text-center').empty().append("<span style='font-size:150%'>&check;</span>");
  }
});
///LOPPU///
```

### Tyhjennä Hae tietokannasta -hakukenttä

Tarpeellisuus: Ei tarpeellinen versiossa 22.11.

```
$(document).ready(function() {
      localStorage.removeItem("searchbox_value");
});
```

### Nidehaun tyhjennys-linkki

Versio: 24.05

```
// Nidehaun tyhjennys linkki.
function tyhjenna_valinnat() {
 window.location.reload(true);
}
$(document).ready(function() {
  $('body#catalog_itemsearch div#toolbar').append('<div class="btn-group"><a onclick="tyhjenna_valinnat(); return false;" href="#" class="btn btn-sm btn-link" id="nidehakuTyhjenna"><i class="fa fa-trash"></i><span> Tyhjennä kentät</span></a></div>');
});
//LOPPU
```

### Haku-kenttien aktivoitumisviive

Korjaa kenttiin kirjoittamisen takkuilun
Tarpeellisuus: Suositeltava (22.11)

```
//ALKU
//Haku-kenttien hakuviiveet
//hyllyvarauslistan haku-kentän hakuviive #826
$(document).ready(function() {
    if (window.location.href.indexOf("/circ/kohasuomi-pendingreserves.pl") > -1) {
        $.holdReady(true);
        setTimeout(function() {

            // Setting a delay after page load to catch dt elements
            $.holdReady(false);
        }, 3000);
        $(document).ready(function() {

            function delay(callback, ms) {
                var timer = 0;
                return function() {
                    var context = this,
                        args = arguments;
                    clearTimeout(timer);
                    timer = setTimeout(function() {
                        callback.apply(context, args);
                    }, ms || 0);
                };
            } 
            var search_thread = null;
            $(".dataTables_filter input")
                .unbind()
                .bind("input", function(e) {
                    clearTimeout(search_thread);
                    search_thread = setTimeout(function() {
                        var dtable = $("#holdst").dataTable().api();
                        var elem = $(".dataTables_filter input");
                        return dtable.search($(elem).val()).draw();
                    },500);
                });
            //Delayed 
        });
    }
});

//tietueen perusnäkymän haku-kentän hakuviive #826
$(document).ready(function() {
    if (window.location.href.indexOf("/catalogue/detail.pl") > -1) {
        $.holdReady(true);
        setTimeout(function() {

            // Setting a delay after page load to catch dt elements
            $.holdReady(false);
        }, 3000);
        $(document).ready(function() {

            function delay(callback, ms) {
                var timer = 0;
                return function() {
                    var context = this,
                        args = arguments;
                    clearTimeout(timer);
                    timer = setTimeout(function() {
                        callback.apply(context, args);
                    }, ms || 0);
                };
            }
            var search_thread = null;
            $("input[aria-controls='holdings_table']")
                .unbind()
                .bind("input", function(e) {
                    clearTimeout(search_thread);
                    search_thread = setTimeout(function() {
                        var dtable = $("#holdings_table").dataTable().api();
                        var elem = $("input[aria-controls='holdings_table']");
                        return dtable.search($(elem).val()).draw();
                    },500);
                });
          $("input[aria-controls='otherholdings_table']")
                .unbind()
                .bind("input", function(e) {
                    clearTimeout(search_thread);
                    search_thread = setTimeout(function() {
                        var dtable = $("#otherholdings_table").dataTable().api();
                        var elem = $("input[aria-controls='otherholdings_table']");
                        return dtable.search($(elem).val()).draw();
                    },500);
                });
        });
    }
});

//hankinnan vastaanoton haku-kentän hakuviive #826
$(document).ready(function() {
    if (window.location.href.indexOf("/acqui/parcel.pl") > -1) {
        $.holdReady(true);
        setTimeout(function() {

            // Setting a delay after page load to catch dt elements
            $.holdReady(false);
        }, 3000);
        $(document).ready(function() {

            function delay(callback, ms) {
                var timer = 0;
                return function() {
                    var context = this,
                        args = arguments;
                    clearTimeout(timer);
                    timer = setTimeout(function() {
                        callback.apply(context, args);
                    }, ms || 0);
                };
            }
            var search_thread = null;
            $(".dataTables_filter input")
                .unbind()
                .bind("input", function(e) {
                    clearTimeout(search_thread);
                    search_thread = setTimeout(function() {
                        var dtable = $("#pending_orders").dataTable().api();
                        var elem = $(".dataTables_filter input");
                        return dtable.search($(elem).val()).draw();
                    },500);
                });
            //Delayed 
        });
    }
});
//LOPPU
```

### Lisää käyttöoikeuksia -valikko Aseta virkailijaoikeuksia -sivulle

Vaskin tekemä js, ei käytössä kaikissa kimpoissa.<br />
Versio: 24.05

```
// Lisää käyttäjäoikeudet monivalintanappi sivulla /cgi-bin/koha/members/member-flags.pl? Pudotusvalikkonappi lisätään lomakkeen yläreunaan ennen Tallenna-nappia.
$(document).ready(function() {
  if ( "body#pat_member-flags.pat" ){
	var asiakaspalvelu = [ "flag-4", "flag-2", "flag-29", "circulate_circulate_remaining_permissions", "circulate_force_checkout", "circulate_manage_restrictions", "circulate_override_renewals", "editcatalogue_edit_items", "editcatalogue_edit_any_item", "plugins_tool", "plugins_report", "reports_execute_reports", "reserveforothers_place_holds", "serials_receive_serials", "tools_items_batchdel", "tools_items_batchmod", "tools_label_creator", "tools_inventory", "updatecharges_manual_invoice", "updatecharges_remaining_permissions", "updatecharges_writeoff" ];
    var kevyttunnus1 = [ "flag-2", "flag-29", "circulate_circulate_remaining_permissions", "circulate_force_checkout", "circulate_override_renewals", "editcatalogue_edit_items", "editcatalogue_edit_any_item", "plugins_tool", "reserveforothers_place_holds", "tools_label_creator", "borrowers_view_borrower_infos_from_any_libraries" ];
    var kevyttunnus2 = [ "flag-2", "flag-29", "editcatalogue_edit_items", "editcatalogue_edit_any_item", "plugins_tool", "tools_items_batchdel", "tools_items_batchmod", "tools_label_creator" ];
    var kuvailu = [ "flag-14", "editcatalogue_advanced_editor", "editcatalogue_edit_catalogue", "tools_records_batchdel", "tools_records_batchmod" ];
    var hankintaJaKausijulkaisut = [ "editcatalogue_advanced_editor", "acquisition_budget_add_del", "acquisition_budget_manage", "acquisition_budget_modify", "acquisition_contracts_manage", "acquisition_group_manage", "acquisition_order_manage", "acquisition_order_receive", "acquisition_period_manage", "acquisition_planning_manage", "acquisition_vendors_manage", "acquisition_delete_baskets", "acquisition_delete_invoices", "acquisition_edit_invoices", "acquisition_merge_invoices", "acquisition_reopen_closed_invoices", "editcatalogue_edit_catalogue", "serials_check_expiration", "serials_claim_serials", "serials_create_subscription", "serials_delete_subscription", "serials_edit_subscription", "serials_receive_serials", "serials_renew_subscription" ];
    var erapaivakalenteri = [ "tools_edit_calendar" ];
	var laskutus = [ "plugins_tool", "flag-10", "borrowers_edit_borrowers", "borrowers_view_borrower_infos_from_any_libraries" ];
	var automaatti = [ "flag-1" ];
    var paakayttaja = [ "flag-0" ];
	
    var oikeudetNappi = "<div class='btn-group'><button class='btn btn-default dropdown-toggle' data-toggle='dropdown'><i class='fa fa-plus'></i> Lisää käyttöoikeuksia <span class='caret'></span></button><ul class='dropdown-menu'><li><a href=# id='asiakaspalvelu'>Asiakaspalvelu</a></li><li><a href=# id='kevyttunnus1'>Kevyttunnus 1</a></li><li><a href=# id='kevyttunnus2'>Kevyttunnus 2</a></li><li><a href=# id='kuvailu'>Kuvailu</a></li><li><a href=# id='hankintaJaKausijulkaisut'>Hankinta ja kausijulkaisut</a></li><li><a href=# id='erapaivakalenteri'>Eräpäiväkalenteri</a></li><li><a href=# id='laskutus'>Laskutus</a></li><li><a href=# id='automaatti'>Automaatti</a></li><li><a href=# id='paakayttaja'>Pääkäyttäjä</a></li></ul></div>";

    $( "#permissions_toolbar button.btn.btn-primary" ).before( oikeudetNappi );
    $( "#permissions_toolbar" ).css("width", " ");
		
	$('#asiakaspalvelu').click( function(){
	  for (i=0; i<asiakaspalvelu.length; i++){
		if ( $('#' +asiakaspalvelu[i]).prop('checked') == false){
	    $('#' +asiakaspalvelu[i]).click();
	    }
	  }
	});
	
	$('#kevyttunnus1').click( function(){
	  for (i=0; i<kevyttunnus1.length; i++){
		if ( $('#' +kevyttunnus1[i]).prop('checked') == false){
	    $('#' +kevyttunnus1[i]).click();
	    }
	  }
	});
	
	$('#kevyttunnus2').click( function(){
	  for (i=0; i<kevyttunnus2.length; i++){
		if ( $('#' +kevyttunnus2[i]).prop('checked') == false){
	    $('#' +kevyttunnus2[i]).click();
	    }
	  }
	});
	
	$('#kuvailu').click( function(){
	  for (i=0; i<kuvailu.length; i++){
		if ( $('#' +kuvailu[i]).prop('checked') == false){
	    $('#' +kuvailu[i]).click();
	    }
	  }
	});
	
	$('#hankintaJaKausijulkaisut').click( function(){
	  for (i=0; i<hankintaJaKausijulkaisut.length; i++){
		if ( $('#' +hankintaJaKausijulkaisut[i]).prop('checked') == false){
	    $('#' +hankintaJaKausijulkaisut[i]).click();
	    }
	  }
	});
	
	$('#erapaivakalenteri').click( function(){
	  for (i=0; i<erapaivakalenteri.length; i++){
		if ( $('#' +erapaivakalenteri[i]).prop('checked') == false){
	    $('#' +erapaivakalenteri[i]).click();
	    }
	  }
	});
	
	$('#laskutus').click( function(){
	  for (i=0; i<laskutus.length; i++){
		if ( $('#' +laskutus[i]).prop('checked') == false){
	    $('#' +laskutus[i]).click();
	    }
	  }
	});
	
	$('#automaatti').click( function(){
	  for (i=0; i<automaatti.length; i++){
		if ( $('#' +automaatti[i]).prop('checked') == false){
	    $('#' +automaatti[i]).click();
	    }
	  }
	});
	
	$('#paakayttaja').click( function(){
	  for (i=0; i<paakayttaja.length; i++){
		if ( $('#' +paakayttaja[i]).prop('checked') == false){
	    $('#' +paakayttaja[i]).click();
	    }
	  }
	});
	
  }
});
//LOPPU
//LOPPU
```
