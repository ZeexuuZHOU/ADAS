# ADAS_Simulation_in_UnrealEngine
## Ziel
Um einen Spurhalteassistent mit Geschwindigkeitsregleung zu entwickeln
## Aufgabe
1. **Szenarioerstellung in Unreal engine**
  - *Erstellung einer einspurigen Teststrecke*
  - *Plazierung des Testfahrzeugs und der Trajektorie*
2. **Algorithmus zur Spurerkennung (Bildverarbeitung durch OpenCV)**
  - *Plazierung eines Kamerasensors am Platz von Rückspiegel*
  - *Übertragung von Kamerabild nach der App "lane_assistant"*
  - *Bildrauschunterdrückung durch Gaussian Filter*
  - *Bereich von Interesse, mittels einer Polygonmaske oder einer rechteckige Maske*
  - *BGR Bild wird in binäres Bild transformiert*
  - *Kantedetektion mit Sobel Operator*
  - *Liniendetektion mittels Hough Transformation*
  - *Beseitigung unwichtiger Linien*
  - *Feststellung der Grenze von Fahrbahn mittels Regression Least squres Methode*
  - *Verbinden die Mittelpunkt des unteren Kante von Kamerabild mit der Mittelpunkt von Fahrbahn, und die gemahlte Linie wird als Fahrrichtung gekennzeichnet*
3. **Querregelung des Fahrzeugs** 
  - *P-Regler*
    - *Eingabe: Der Winkel zwischen die vertikale Mittellinie des Kamerabilds und die Fahrrichtung*
    - *Ausgabe: Linkwinkel zwischen -1 und +1*
4. **Längsregelung des Fahrzeugs**
  - *Informationserfassung von eigener Geschwindigkeit mittels Positionssensor*
  - *Informationserfassung von Distanz zum vorausfahrenden Fahrzeug mittels Objektlistensensor*
  - *PD-Regler*
    - *Eingabe: Die Distanz zum vorausfahrenden nächsten Fahrzeug*
    - *Ausgabe: Gaspedal zwischen -1 und +1*
## Ergebnis
<img src="https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/Bildverarbeitung.gif" height="400" />
<img src = "https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/Bremse.gif">
## Schwächen

