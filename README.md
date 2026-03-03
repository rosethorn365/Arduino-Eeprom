HARJOITUS 4.3 
  Ohjelma mittaa lämpötilaa 5 sekunnin välein ja tallentaa sen EEPROM-muistiin silloin,
  kun mittausarvo muuttuu. Painonapeilla voi tulostaa tai tyhjentää muistia
  
  LÄMPÖTILAN MITTAUS
  ----------------------------
  - Anturi on kytketty analogipinniin A0.
  - Ohjelma lukee anturilta 50 ADC-arvoa 
  - Nämä 50 arvoa summataan ja niistä lasketaan keskiarvo avgADC
  - Ohjelma seuraa aikaa millis()-toiminnolla
  - Jos uusi avgADC on eri kuin edellinen mitattu avgADC, tallennetaan uusi merkintä EEPROMiin
  - Jos arvo ei muutu, mitään ei tallenneta
  - EEPROMiin tallennetaan aina kaksi arvoa peräkkäin, aika ja avgADC
  - Ohjelma pitää muuttujassa muistipaikan, mihin seuraava merkintä kirjoitetaa
  - Kun merkintä on kirjoitettu, osoitetta kasvatetaan seuraavaa tallennusta varten
  - Jos muisti tulee täyteen, kirjoittaminen aloitetaan uudelleen EEPROMin alusta
  - Lämpötila lasketaan LT = ((5 * avgADC / 1024.0) - 0.5) * 100
  - Painonappi pinnissä 3 tulostaa EEPROM-muistin sarjaporttiin 
  - Painonappi pinnissä tyhjentää EEPROM-muistin (kirjoittaa 0kaikkiin paikkoihin)
