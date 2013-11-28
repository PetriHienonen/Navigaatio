Class locator
==========

YO YO YO! Tehdäänkin jokaiseen osioon oma tiedosto eikä kirjoteta kaikkee tähän filuun. BOOM!










Ryhmä:
Rami Pulkka, Niklas Törnblom, Petri Hienonen, Patrick Gyllebögel

Ryhmännimi: 

Päiväys: 
5.11.2013









1. Johdanto

Projektimme Classlocator on navigaatio-ohjelmisto, joka helpottaa Leppävaaran Metropolia Ammattikorkeakoulussa navigointia. Ohjelmisto toimii samalla tyylillä kuin Google street view, mutta katukuvien sijasta ohjemistossa navigoidaan koulussamme. Ohjelmiston on tarkoitus auttaa niin opettajia kuin oppilaitakin navigoimaan itsensä lukujärjestyksen mukaiselle seuraavalle oppitunnille, tai etsimään jokin tietty luokka.

Classlocator on käytännöllinen ohjelmisto, joka syrjäyttää oitis koulun seinillä roikkuvat pohjapiirrustukset joista luokkien sijainnit saa selville, sekä käytävillä olevat koneet joissa on lukujärjestysohjelmistot, jotka kertovat vain luokan nimen, muttei sijantia. Ohjelmisto neuvoo kuvien avulla tarkasti mihin suuntaan pitää kulkea löytääksesi oikeaan luokkaan, ja ohjelmistosta löytyy myös kirjautuneen henkilön oma henkilökohtainen lukujärjestys. Ohjelma toimii samoilla tunnuksilla joilla käytetään koulun Tuubi-sivustoa, ja se on lähinnä tarkoitettu käytettäväksi älypuhelimilla. 

Tässä raportissa esittelemme projektiamme Classlocator:ia, kuinka sitä käytetään, kuinka se toimii ja mitä ominaisuuksia se pitää sisällään. Ohjelmistoa esitellään kaavioiden, kuvien ja esimerkkien avuin. Ohjelma on helppokäyttöinen, ja se tekee koulussa navigoimisesta yksinkertaista. 


2. Käyttötapaukset

Classlocator -ohjlelmistoa voi käyttää Metropolian kaikki joilla on metropolian tunnukset, eli oppilaat ja opettajat. Jaoittelimme tähän mitä nämä edelä mainitut kaksi käyttäjäryhmää voivat ohjelmistolla tehdä.

Metropolian opiskelijat voivat etsiä koulusta luokkaa nimen tai seuraavan oppitunnin mukaan. Ohjelmistossa löytyy kirjautuneen oppilaan oma lukujärjestys, jonka avulla voi navigoida itseään luokkaan jossa seuraava oppitunti on. Opiskelija voi myös etsiä jotain tiettyä varaamatonta luokkaa. Myös opettajilla ovat samat ominaisuudet käytössään.

!!!!!!Teimme kolme erilaista käyttötapauskaaviota. Ensimmäinen kaavio kuvaa tapahtumien kulkua kun luokkaa haetaan lukujärjestyksen avulla seuraavaa oppitunnin sijaintia etsiessä. Toinen kaavioista kuvaa luokan itse määriteltyä hakua, ja vimeinen on yleiskatsaus koko ohjelmiston käytöstä

(eka kuva) 
(toka kuva)
(kolmas kuva)!!!!!! TÄÄ MENI VISSII JO VITUIKS KU SEKOTIN VUOKAAVION JA KÄYTTÖTAPAUSKAAVION. EN HEITÄNY VIEL TEKSTEJÄ MENEE JOS KÄYTTÄÄ NIITÄ JOSSAI

Ohjelmiston alkutilassa on kirjautumissivu, josta pääsee etenemään syöttämällä tunnukset nille takoitetulle kentille. Seuraavaksi valitaan halutaanko käyttää lukujärjestelmäpohjaista navigointia vai vapaata reitin hakua. Kun haluttu vaihtoehto on valittu, ohjelmisto kysyy GPS-järjestelmän käynnistymisestä/käyttämisestä, jos valitaan kyllä, ohjelmisto hakee lähtöpaikan GPSn avulla. Jos taas valitaan ei, lähtöpaikan voi itse kirjoittaa viestikenttään, tai sitten lähtöpaikan voi valita pudotusvalikon listasta. Tämän jälkeen lukujärjestyspohjaisessa valinnassa ohjelmisto lisää automaattisesti kohteen luokan nimen, jonka voi itse kirjoittamalla korjata jos ohjelma tekee virheen. Tämän jälkeen painetaan vain hakua, ja ohjelmisto hakee lyhimmän reitin. Itsevalintaisessa luokan haussa kohdeluokan nimi kirjoitetaan itse tai valitaan pudotuslistasta, ja painetaan hae-nappia.

Kun reitti on asetettu, näytölle tulee Google street viewia muistuttava näkymä, eli voit hyppiä kuva kerralla esim. pitkin koulun käytäviä, ja ohjelmisto piirtää sinistä viivaa lattiaan siihen suuntaan mihin ollaan navigoimassa. Perille päästessä näyttöön tulee ilmoitus että kohteeseen on saavuttu. Tämän yhteydessä voi valita haluaako poistua ohjelmasta vai tehdä uuden haun.

3. Järjestelmäarkkitehtuuri

Käyttäjätietokanta

Karttapalvelun käyttäminen (Kuvapankki)

Lukkarikone

Gps navigointi yhdessä karttapalvelun kanssa?














Jees jees, homma rullaa! Kloonit tehty ja koko ryhmä on ajantasalla. T. Peppe

Tiedosto Harjoitus3 lisätty. T:Rami


Jees jees, hyvä homma. Jengi vois merkkaa kuka kommas. t. pate


Hienoo duunii pojat!! T: Nikke
