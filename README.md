# ADAS_Simulation_in_UnrealEngine
## Notiz über die Programme Lane_assistant.cpp
Ich habe das Programm allein abgeschlossen. In Lane_assistant.cpp gibt es schon vorgegebene Teile, die Main loop und die Kommunikation zwischen VScode und Unreal Engine beinhaltet, und Ich habe die Funktion processData(), detectLanes(), processObject(), denoise(), cropping_rectangle(), cropping_polygon(), toBinary(), toBinary_white(), edgeDetection(), lineDetection(), steeringAngle(), velocityController() geschrieben.
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
## Ergebnis(GIF)
1. Bildverarbeitung(von Linke nach Rechte: Kamerabild - Bereich von Interesse - Binäres Bild - Kantedetektion - Liniendetektion)
<img src="https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/Bildverarbeitung.gif" >  
  
2. Bremsen  
<img src = "https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/Bremse.gif">  
  
3. Folgen 

langsam fahren(10 km/h):

<img src = "https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/Folgen.gif">

schnell fahren(60 km/h):  

<img src = "https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/Folgen2.gif"> 

5. Überholen 
<img src = "https://github.com/ZeexuuZHOU/ADAS_Simulation_in_UnrealEngine/blob/main/U%CC%88berholen.gif"> 

## Schwächen
1. **Schlechte Robustheit bei Spurerkennung in folgende Szenen**:
  - *Schnee*
  - *Reflektion aus dem glatten Boden*
  - *Andere Symbole auf dem Boden*
  
2. **Nur verfügbar bei Autobahn, Keine Verfügbarkeit bei größer Krümmung oder Kreuzung**
3. **Nicht fähig, Fahrbahn zu wechseln und vorausfahrendes Fahrzeug intelligent zu überholen**
