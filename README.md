# ADAS_Simulation_in_UnrealEngine
## Ziel
Um einen Spurhalteassistent mit Geschwindigkeitsregleung zu entwickeln
## Aufgabe
1. **Szenarioerstellung in Unreal engine**
  - Erstellung einer einspurigen Teststrecke
  - Plazierung des Testfahrzeugs und der Trajektorie
3. **Algorithmus zur Spurerkennung (Bildverarbeitung durch OpenCV)**
  - Plazierung eines Kamerasensors am Platz von Rückspiegel
  - Übertragung von Kamerabild nach der App "lane_assistant"
  - Bildrauschunterdrückung durch Gaussian Filter
  - ROI, mittels einer Polygonmaske oder einer rechteckige Maske
  - BGR Bild wird in binäres Bild transformiert
  - Kantedetektion mit Sobel Operator
  - Liniendetektion mittels Hough Transformation
  - Beseitigung unwichtiger Linien 
  - Feststellung der Grenze von Fahrbahn mittels Regression Least squres Methode
5. **Querregelung des Fahrzeugs** 
6. **Längsregelung des Fahrzeugs**
## Ergebnis
