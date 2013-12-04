Classlocator
==========

Ryhmä: 
Rami Pulkka 
Niklas Törnblom 
Petri Hienonen 
Patrick Gyllebögel

Ryhmännimi: Navigaatiopojat 

Päiväys: 5.12.2013


Käyttötapaukset
---------------

Classlocator -ohjelmistoa voi käyttää kaikki joilla on metropolian tunnukset, eli oppilaat ja opettajat.Jaoittelimme 
tähän mitä nämä edellä mainitut kaksi käyttäjäryhmää voivat ohjelmistolla tehdä. Metropolian opiskelijat ja opettajat 
voivat etsiä koulusta luokkaa nimen tai seuraavan oppitunnin mukaan. Ohjelmistossa löytyy kirjautuneen oppilaan oma 
lukujärjestys, jonka avulla voi navigoida itseään luokkaan jossa seuraava oppitunti on. Käyttäjä voi myös etsiä jotain 
tiettyä varaamatonta luokkaa.

![alt text](https://users.metropolia.fi/~niklasto/Git/Kuvat/Käyttötapakaavio.png "Käyttötapakaavio")

Kaaviossa näytetään miten ohjelmistoa käytetään, askel askeleelta.

Ohjelmiston alkutilassa on kirjautumissivu, josta pääsee etenemään syöttämällä tunnukset niille tarkoitetulle kentille.
Seuraavaksi valitaan halutaanko käyttää lukujärjestelmäpohjaista navigointia esim. jos etsitään missä seuraava 
oppitunti on, tai sitten vapaata luokan hakua jos halutaan vain mennä johonkin tiettyyn luokkaan tekemään 
kouluprojekteja. Kun haluttu hakuvaihtoehto on valittu, ohjelmisto kysyy GPS-järjestelmän käynnistymisestä/käyttämisestä,
jos valitaan kyllä, ohjelmisto hakee lähtöpaikan GPSn avulla. Jos taas valitaan ei, lähtöpaikan voi itse kirjoittaa 
viestikenttään, tai sitten lähtöpaikan voi valita pudotusvalikon listasta. Tämän jälkeen lukujärjestyspohjaisessa 
valinnassa valitaan seuraava oppitunti, josta ohjelmisto lukee luokan nimen ja asettaa sen päämääräksi. Tämän jälkeen
painetaan vain hakua, ja ohjelmisto hakee lyhimmän reitin. Manuaalisessa luokan haussa kohdeluokan nimi kirjoitetaan 
itse tai valitaan pudotuslistasta. Tämän jälkeen painetaan hae-nappia ja navigointi alkaa.

Kun reitti on asetettu, näytölle tulee Google street viewia muistuttava näkymä, eli voit hyppiä kuvia eteenpäin kohti
päämäärää pitkin koulun käytäviä painamalla nuolen kuvaa, tai jos käytössä on GPS, kuva päivittyy itsestään muutaman 
metrin välein. Ohjelmisto piirtää sinistä viivaa lattiaan siihen suuntaan mihin ollaan navigoimassa. Perille päästessä näyttöön tulee ilmoitus että kohteeseen on saavuttu. Tämän yhteydessä voi valita haluaako poistua jossa voi kirjautua ulos ja lopettaa ohjelman painamalla kyllä, tai sitten käyttäjä voi halutessaan palata ohjelmisto etusivulle painamalla ei.

Teimme kaksi erilaista vuokaaviota ohjelmiston toiminnasta. Alapuolella ensimmäinen kaavio kuvaa tapahtumien kulkua 
kun luokkaa haetaan lukujärjestyksen avulla seuraavaa oppitunnin sijaintia etsiessä. Toinen kaavioista kuvaa luokan
itse määriteltyä hakua.

![alt text](https://users.metropolia.fi/~niklasto/Git/Kuvat/Luokkahaku.png "Vuokaavio1")
  Kuva selventää ohjelmiston toimintaa yksityiskohtaisesti, kun nagivoidaa kohti päämäärää kun valittuna on luokan haku.


![alt text](https://users.metropolia.fi/~niklasto/Git/Kuvat/Lukkarihaku.png "Vuokaavio2")
  Kuva kertoo kuinka ohjelmisto toimii kun valitaan lukujärjestyksen tarkastelu ja navigointi lukkarikoneen kautta.

Järjestelmäarkkitehtuuri
=======================

Käyttäjätietokanta
------------------

Käyttäjinä toimivat Leppävaaran Metropolia ammattikorkeakoulun opiskelijat ja opettajat. 
ClassLocator:iin kirjaudutaan Tuubi-tunnuksilla, jonka avulla järjestelmä tunnistaa käyttäjän. 
Opiskelija-ja opettajarekisteri löytyy Metropolian omasta järjestelmästä.


Karttapalvelun käyttäminen GPS:ssän avulla
-------------------------------------------

Kun käyttäjä hakee luokkaa hän voi valita laitetaanko GPS päälle vai ei. Mikäli GPS:ssä ei haluta päälle,
niin käyttäjällä on mahdollisuus valita lähtöpaikka manuaalisesti listasta tai kirjoittaa lähimmän luokan nimi itse. 

Mikäli GPS laitetaan päälle, niin se paikantaa automaattisesti sijaintisi mobiililaitteen avulla. Tämän jälkeen ruudulle
ilmestyy sininen viiva, jota seuraamalla löytää halutun luokan. Mikäli ei kävele reittiä pitkin, niin laite pyrkii 
löytämään uuden reitin mahdollisimman nopeasti. Tätä järjestelmää varten on olemassa suuri kuvapankki, ja kun 
kävelet reittiä pitkin kuva päivittyy aina muutaman metrin välein.

Ongelmana tässä on että GPS ei tunnista missä kerroksessa ollaan, joten sen jälkeen kun GPS on valittu, sovellus 
kysyy: "Missä kerroksessa olet?" Tätä ongelmaa ei ole kun lähtöpaikka valitaan manuaalisesti, sillä järjestelmä 
tunnistaa luokan minkä edestä lähdetään. 

Lukkarikone
--------------

Mikäli käyttäjä haluaa paikantaa esimerkiksi seuraavan tunnin luokan nopeasti, valitaan aluksi lukkari, joka vie hänet
lukujärjestykseensä. Tässä käyttäjä yhdistetään Tuubin kautta omaan lukkarikoneeseensa. Lukujärjestyksestä voidaan 
painaa haluttu tunti, jonka jälkeen valitaan aloita navigaatio.

Vaatimukset (jäljitettävässä, (mitattavassa) muodossa)
======================================================

 Funktionaaliset vaatimukset
----------------------------

![alt text](http://users.metropolia.fi/~petrihie/Funktionaaliset%20vaatimukset.jpg "Table")


Ei-funktionaaliset järjestelmävaatimukset
----------

4.2 Helppokäyttöisyys

Sovelluksesta on tarkoitus tulla helppokäyttöinen, tulokseen pääsemme siten että käyttäjä ymmärtää mahdollisemman
nopeasti miten sovellus toimii. Esimerkki sovelluksina käytämme erilaisia jo käytössä olevia mobiilisovelluksia 
joissa haut ja muut halutut toiminnot toimivat muutamalla painalluksella. Yritämme lisätä helppokäyttöisyyttä myös
siten että pidämme sovelluksen mahdollisimman selkeänä ja yksinkertaisena. Helppokäyttöisyyttä lisää myös sovelluksen
visuaalinen ilme, eli sovelluksen yleisnäky ja väritys on yhteinäinen. Myös sovelluksen eri elementtejen tulee olla 
tarpeeksi isoja ja erillään toisistaan.

4.3 Luotettavuus

Sovelluksen luottettavuuden takaa sen pohjalla toimiva tuubi-porttaali. Luotettavuutta pyritään lisäämään ennen 
aikaisilla betatestaajilla ja huolellisella toteutuksella. Betatestaajien avulla pystymme korjaamaan mahdolliset 
virheet ennen sovelluksen julkaisemista. 

Mahdollisia järjestelmävirheitä:
      
      -Sovellus ei saa yhteyttä verkkoon.
        .Ratkaisu: kartan, sekä käyttäjän henkilökohtaisen lukujärjestyksen pystyy lataamaan ns. offline tilaan.
      -Sovelluksen luokat eivät ole ajantasalla ja täten navigoi käyttäjän väärään luokkaan.
        .Ratkaisu: Sovellukseen pitää luoda automaattinen päivitysohjelma, joka tarkastaa aina ohjelman avauduttua 
        uusimmat päivitykset.

4.4 Tehokkuus

Sovellus ei tule itsessään olemaan kovinkaan raskas, sillä käyttäjä käytännössä käyttää tuubi-portaalin palvelintilaa
ja navigoinnissa joko puhelimen omaa internetyhteyttä tai koulun wlanverkkoa. Tehokkuus saadaa varmistettua sovellukseen
hyvällä suunnittelulla, yksinkertaisella rakenteella ja mahdollisimman helpolla sekä vähäisellä ohjelmistokoodilla. 

4.5 Muita ei-funktionaalisia vaatimuksia

Ennen sovelluksen toteuttamista pitäisi tietää budjetti. Tämän myötä pystyttäisiin palkkaamaan budjetille sopiva 
työryhmä ja kartoittamaan aikataulu. Sovelluksen tulee olla toteutettu omalle kohderymälle, eli tässä tapauksessa 
Metropolian opiskelijoille ja opettajille ketkä asioivat leppävaaran toimipisteessä. Sovellus pitää sisällään ainostaan
sille tarpeellisia asioita ja sen pitäisi toimia moiteettomasti monella eri mobiilialustalla.

Käyttöliittymä
==============

Tässä osiossa esitellään järjestelmän käyttöliittymien näkymät. Näkymät on esitelty käyttötapauksien mukaan ja ovat 
seuraavalaisia: Ensimmäinen käyttäjätapaus - Navigointi lukujärjestystä käyttäen:

![alt text](http://users.metropolia.fi/~niklasto/Git/Kuvat/Lukkari.png "Lukkari")

Toinen käyttäjätapaus - Navigaatio hakua käyttäen.
![alt text](http://users.metropolia.fi/~niklasto/Git/Kuvat/EtsiLuokka.png "Lukkari")

Käydäänpä läpi näkymiä yksitellen (siirrytään puhelinkuvissa vasemmalta oikealle). Näkymien väliset siirtymät tapahtuvat
sen verran nopeasti, että niihin ei ole erikseen luotu mitään. Näkymä "vain vaihtuu" toiseksi.

+ Ensimmäinen näkymä - Kirjautuminen
    
    - Ohjelmisto vaatii käyttäjältä kirjautumisen Tuubi-järjestelmään. Kun ohjelman avaa, aukeaa heti Tuubin 
      kirjautusmisikkuna. Tähän syötetään käyttäjän Tuubi-tunnus ja salasana, jonka jälkeen painetaan "login" nappia. 
      Tästä siirrytään seuraavaan näkymään.

+  Toinen näkymä - Päävalikko
    
    - Onnistuneen kirjautumisen jälkeen ohjelma siirtyy automaattisesti päävalikkoon. Päävalikossa on kolme valittavaa 
    siirtymävaihtoehtoa: 1. Lukkarikone, 2. Luokka, 3. Signout. Ensimmäisen napin painallus hakee automaattisesti 
    järjestelmästä käyttäjän lukujärjestyksen, synkronoi sen laitteen kellon kanssa (pwm. ja aika) ja siirtää käyttäjän
    lukkarikoneeseen.

Toinen nappi siirtää käyttäjän "luokkahakuun". Tämän  vaihtoehdon valitessa käyttä siirtyy GPS-aktivointi -näkymään, 
joka on samannäköinen kuin siirryttäessä lukkarikoneen kautta, mutta käyttömerkitys on hieman erilainen (lisää kohdassa
4.). Kolmas nappi on tarkoitettu ohjelman sulkemiseen, sitä painamalla käyttäjä kirjautuu automaattisesti ulos 
järjestelmästä ja sulkee ohjelman.

+ Kolmas näkymä - Lukkarikone (käyttäjätapaus 1)

  - Kun käyttäjä on siirtynyt lukkarikoneeseen, on järjestelmä samalla synkronisoinut puhelimen kellon 
    lukujärjestykseen. Käyttäjä itse näkee lukkarikoneen ja siinä kyseisen viikon lukujärjestyksen. Lukkarikonetta voi
    käyttää normaalisti. Käyttäjä näkee myös kaksi nappia lukkarikoneen alla; 1. Aloita navigaatio, 2. Takaisin. 

Ensimmäisen napin painallus laittaa alulle automaattisen navigaation. Koska järjestelmä on lukkarikonetta aukaistessa
jo synkronoinut lukujärjestyksen puhelimen kellon kanssa, aloittaa ohjelma navigoinnin kohti sitä luokkaa, joka on 
puhelimen kellon ja lukkarikoneen mukaan sillä hetkellä käynnissä. Mikäli haku tehdään sellaiseen aikaan, kun on 
esimerkiksi "tauko" eli esimerkiksi tunti alkaa vasta 5min kuluttua, osaa järjestelmä valita automaattisesti seuraavan
tunnin luokan ja aloittaa navigaation sitä kohti. Kun navigaatio alkaa, siirrytään seuraavaan näkymään.Takaisin napin
painallus aiheuttaa ohjelman siirtymisen takaisin päävalikko-näkymään.

+ Neljäs näkymä - GPS-aktivointi (käyttäjätapaus 1 ja 2 [tässä 3. näkymä])

  - Koska useassa älypuhelimessa GPS-käyttö tarvitsee hyväksyä käyttäjän puolesta, kysyy tämäkin ohjelma oikeuksia
    käyttäjältä siihen. Kun navigointi (käyttäjätapaus 1.) on haluttu aloittaa aukeaa siis GPS-aktivointi näkymä. Tässä 
    näkymässä kysytään käyttäjältä yksinkertaisesti, että "aktivoidaanko gps?". Oikeudet voidaan antaa, tai vastaavasti 
    olla antamatta, "Kyllä" ja "Ei" nappien avulla.  Kyllä napin painallus osoittaa puhelimelle, että käyttäjä on antanut
    oikeudet kytkeä GPS-päällä, jonka puhelin antaa hyväksynnän ja ohjelma kytkee sen päälle. Ei nappi taas ei anna
    oikeuksia kytkeä GPS-päälle, ja siirtää käyttäjän takaisin lukkarikoneeseen. GPS-yhteyden valitseminen hakee
    automaattisesti puhelimen sijainnin.

  - Käyttäjätapauksessa kaksi (2), jossa haetaan luokkaa valitsemalla päämäärä, tai vaihtoehtoisesti alkupiste ja 
  päämäärä, on mahdollista käyttää navigaatiota ilman GPS-hakua. Mikäli käyttäjä on siis valinnut päävalikkonäkymästä 
  kohdan "Luokka", ja siirtynyt "GPS-aktivointi" -näkymään, voi hän ilman gps-aktivointia silti selata manuaalisesti 
  navigointinäkymää. Eli siis mikäli käyttäjä siirtyy tähän näkymää käyttäjätapaus 2:den -mukaisesti, hän pääsee 
  EI-nappia painamalla seuraavaan näkymään.
  
  - Huomattavaa on siis, että Navigointi ilman GPS-onnistuu ainoastaan "luokkahaun" kautta. Mikäli käyttäjä haluaa 
  navigoida lukkarikoneen kautta, hänen on siis käytettävä GPS-yhteyttä

+ Neljäs näkymä - Luokkahaku (käyttäjätapaus 2) 

  - Tähän näkymään päästäkseen käyttäjä on valinnut päävalikosta toisen napin. GPS-näkymästä hän on valinnut jomman 
    kumman vaihtoehdon. Näkymässä on kaksi vierityspalkkia joihin käyttäjä voi kirjoittaa luokan; ensimmäinen on 
    "Lähtöpaikka" ja toinen "Päämäärä". Näitten palkkien alapuolella on "Hae" -nappula. Vierityspalkeista voi joko 
    valita luokat selaamalla vierityspalkkia, tai sitten kirjoittamalla luokan nimen. Nimillä tarkoitetaan luokkien 
    numerokoodeja, esim. B302. Isot ja pienet kirjaimet kelpaavat.

  - Mikäli käyttäjä valitsi GPS-näkymässä käyttävänsä GPS-toimintoa, hänen ei tarvitse laittaa lähtöpaikkaansa. Mikäli 
    hän tässä tapauksessa kirjoittaa lähtöpaikkansa, sitä ei oteta huomioon. Käyttäjän tulee kirjoittaa päämäärä, tai 
    hän ei pääse valikosta eteenpäin. Päämäärän valittua, käyttän tulee painaa "Hae"-nappia, jonka jälkeen käyttäjä 
    siirtyy navigaationäkymään.

  - Mikäli käyttäjä valitsi ettei käytä GPS-yhteyttä, hänen tulee kirjoittaa päämäärän lisäksi myös lähtöpaikka. Tämän 
    jälkeen "hae"-napin painalluksella käyttäjä siirtyy GPS-yhteydettömään navigaationäkymään.

+ Viides näkymä - GPS-yhteydellinen navigaatio (ylemmän kuvan 5. puhelin)

  - Tähän näkymään käyttäjä on päässyt siis, joko lukkarikoneen kautta, tai valitessaan luokkahaussa GPS-yhteyden 
    käytön. GPS-aktivointi on hakenut automaattisesti puhelimen sijainnin ja näkymä aukeaa puhelimen sijainnissa. 
    Näkymässä näkyy koulun käytäviltä otettuja kuvia streetview-tyylisesti. Kuvien keskellä menee sininen läpinäkyvä 
    viiva, joka osoittaa käyttäjälle minne tulee mennä. Näkymässä on myös kaksi nappia; "Takaisin" ja "Etusivu". 
    Etusivu-nappi siirtää lopettaa navigaation ja avaa päävalikon. Takaisin-nappi taas avaa edellisen nähdyn näkymän, 
    eli käyttäjätapaus 1:n kohdalla "lukkarikoneen", tai käyttäjätapaus 2:n kohdalla "luokkahaun". Kun käyttäjä 
    liikkuu sinisen viivan mukaisesti, lataa näkymä aina uutta valokuvaa sijainnin mukaan. Valokuvat ladataan 
    serveriltä kuvapankista. Kun määränpäähän on päästy, tunnistaa ohjelma sen ja avaa viimeisen, eli "päämäärä"-
    näkymän.

+ Viides näkymä - GPS-yhteydetön navigaatio (käyttäjätapaus 2)

    - Tähän näkymään käyttäjä on päässyt, kieltämällä GPS-käytön ja valitsemalla päämäärän lisäksi lähtöpaikan. Ohjelma
      lataa kuvapalvelimelta nökymään kuvan, joka on löhimpänä lähtöpaikkaa. Näkymä muistuttaa GPS-yhteydellistä näkymää
      muuten, mutta erona sinisessä viivassa näkyvä nuoli. Tämä nuoli on itseasiassa nappi, jota painamalla ohjelma lataa
      kuvapankista seuraavankuvan. Tämä navigaatio on siis manuaalinen ja jokainen kuvanlataaminen tapahtuu nuolta 
      painamalla, toisin kuin yhteydellisessä näkymässä, jossa kuvat ladataan GPS-sijainnin perusteella. Näkymässä 
      olevat "Etusivu" ja "Takaisin"-napit toimivat kuten yhteydellisessä näkymässä. Kun käyttäjä on tarpeeksi useasti
      painanut nuolinappia ja ohjelma tunnistaa että ladattu kuva on päämäärä, avaa ohjelma silloin "päämäärä"-näkymän.
    
+ Kuudes näkymä - Päämäärä

    - Päämäärä näkymä, on ns. viimeinen käyttäjän näkemä näkymä ohjelmaa selatessa. Se aukeaa, kun ohjelma tunnistaa,
      että käyttäjä on navigoinut haluamaansa päämäärään. Näkymä on samankaltainen kuin navigaationäkymä, mutta sen 
      päälle ilmestyy hieman läpiväkyvä "laatikko", joka ilmoittaa, että käyttäjä on saavuttanut päämääränäsä. Tämän
      lisäksi siinä kysytään, että haluaako käyttäjä sulkea ohjelman. Mikäli käyttäjä painaa "Kyllä"-nappia, ohjelma 
      kirjaa käyttäjän ulos ja sulkeutuu. Jos käyttäjä taas painaa "Ei"-nappia, palaa hän alkuvalikkoon.


