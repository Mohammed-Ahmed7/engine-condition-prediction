#  Engine Condition Prediction

##  About the Project
Ich habe dieses Projekt gemacht, um Machine Learning zu lernen und praktisch auszuprobieren.  
Die Idee Kann man mit Sensordaten vorhersagen ob ein Motor gesund oder ungesund ist?  
Alles sollte in der Notebook kommentiert sein.

Es ist kein Industrieprojekt sondern ein **Lernprojekt**.  
Mir war wichtig, eine komplette ML-Pipeline von vorne bis hinten zu verstehen:  
Daten anschauen -> Muster und Zusammenhänge finden -> Ein Modell trainieren  -> Am Ende auswerten ob das Modell überhaupt sinnvoll ist  

## Tools
Python Bibliotheken: pandas, seaborn, matplotlib, scikit-learn  
Jupyter Notebook  
Modell: Random Forest  

## What is Random Forest (einfach erklärt)
Stell dir vor, du fragst 500 verschiedene Mechaniker 
Ist dieser Motor gesund oder nicht?  
Jeder Mechaniker schaut sich 2 Sensorwerte an beispiel Drehzahl, Temperatur. 
(Mechaniker bekommen nicht alle sensor daten max_features{default=”sqrt”}) heisst die Wurzel von anzahl Feature 6
Jeder trifft eine Entscheidung.  
Am Ende stimmen alle ab -> die Mehrheit entscheidet.  

Genau so arbeitet Random Forest.  
Viele kleine Entscheidungsbäume -> eine große robuste Entscheidung.  

**RandomForestClassifier — scikit-learn 1.7.1 documentation**
https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html

## My Workflow
Daten: Grundlegende Statistiken und Verteilungen angesehen  
Heatmap erstellt um Zusammenhänge zwischen Sensorwerten zu finden  

Vorbereitung:
Ziel ist Engine Condition (0 = ungesund, 1 = gesund) zu vorhersagen  
Train/Test Split (85 % / 15 %)  

Training:
Random Forest mit 500 Bäumen  
class_weight="balanced" um die Daten auszugleichen  

**Evaluation**:
Accuracy ~65 %  
Gesunde Motoren gut erkannt  
Ungesunde Motoren schlecht erkannt  

## Probleme:
**Daten unausgeglichen** Es gibt fast doppelt so viel gesunde Motore als ungesunde.  
Dadurch hat das Modell gelernt Motor ist meistens gesund

**Genauigkeit nur 65 %** mehr Daten oder bessere Features gebraucht.  
Manche Korrelationen wie Temperatur ergeben garkein Sinn durch hohe Temperaturen gibt es sehr schnell Motorschaden.  

## What can be improved Ideen für die Zukunft
Mehr Modelle ausprobieren wie XGBoost.

Größeren Datensatz verwenden ich brauche viel mehr ungesunde Beispiele damit das Modell besser lernt und ungesunde Motoren besser erkennt.

Jetzige aufteilung der Daten ist 63% gesund 37% ungesund.
Eine **App oder API** bauen die live eine Diagnose macht von grade neuen erstellten Daten.

##  Conclusion:
Dieses Projekt war mein ersterSchritt in Machine Learning.  
Das Modell ist mit 65% genauigkeit noch weit weg von praxisreif aber
Ich habe verstanden wie eine ML-Pipeline funktioniert.  
Ich weiß wo die Schwächen sind.  
und viele ideen was man mit ML machen kann. 
