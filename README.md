# Star Type Classification - NASA Stars Gruppenarbeit

## Gruppenmitglieder

- Mona Auer
- Leni Biasi
- Dana Kando

## Projektbeschreibung 
In unserem Projekt wird das Star Type Classification Dataset analysiert. Unser Ziel ist es, anhand physikalischer und spektraler Merkmale vorherzusagen, zu welcher Sternklasse ein Objekt gehört.

Die Zielvariable ist `Type`. Sie beschreibt sechs verschiedene Sternklassen:

| Type | Sternklasse |
| --- | --- |
| 0 | Red Dwarf |
| 1 | Brown Dwarf |
| 2 | White Dwarf |
| 3 | Main Sequence |
| 4 | Super Giants |
| 5 | Hyper Giants |

Das Projekt umfasst das Laden, Explorieren, Bereinigen und Modellieren des Datensatzes. Die finale Machine-Learning-Pipeline befindet sich in unserem Jupyter Notebook `star_type_classification.ipynb`.

## Datensatz

Die Datei `nasa_stars_data.csv` enthält 240 gültige Beobachtungen mit folgenden Merkmalen:

| Spalte | Beschreibung |
| --- | --- |
| `Temperature` | Oberflächentemperatur des Sterns in Kelvin |
| `L` | Relative Leuchtkraft im Vergleich zur Sonne |
| `R` | Relativer Radius im Vergleich zur Sonne |
| `A_M` | Absolute Magnitude / intrinsische Helligkeit |
| `Color` | Beobachtete Farbe des Sterns |
| `Spectral_Class` | Spektralklasse nach dem Harvard-System |
| `Type` | Zielvariable für die Sternklasse |

Beim Laden der Datei mussten einige Besonderheiten beruecksichtigt werden:

- Die Datei verwendet `~` als Trennzeichen.
- Vor der eigentlichen Kopfzeile steht eine Beschreibungszeile.
- Rechts neben den relevanten Spalten befinden sich leere Zusatzspalten.
- Beim Laden entstehen durch leere Zeilen zunächst zusätzliche Datensaetze ohne Zielvariable; diese werden im Cleaning entfernt.
- Es gibt fehlende Werte in mehreren Spalten.
- Die Spalte `Color` enthält uneinheitliche Schreibweisen und einzelne Tippfehler.
(Blöööd aber das können wir als Data-Scientists das Michael lösen!)

Die Originaldatei wurde von uns dafür natürlich nicht manuell verändert. Alle Bereinigungsschritte die wir gemachht haben haben wir im Notebook nachvollziehbar dokumentiert.

## Machine-Learning-Ansatz
Das Projekt wurde als überwachtes Klassifikationsproblem umgesetzt.

Verwendete Features:
- Numerische Features: `Temperature`, `L`, `R`, `A_M`
- Kategoriale Features: `Color`, `Spectral_Class`

Die Preprocessing-Pipeline umfasst:
- Umwandlung numerischer Spalten
- Vereinheitlichung von Farbkategorien
- Behandlung fehlender Werte
- Skalierung nummerischer Variablen
- One-Hot-Encoding kategorialer Variablen

Anschliessend wurden mehrere Klassifikationsmodelle verglichen:
- Logistic Regression
- Support Vector Machine
- Random Forest

Die Modellbewertung erfolgt mit Accuracy, Macro F1 Score, Cross Validation, Classification Report und Confusion Matrix.


## Projektdateien

| Datei | Inhalt |
| --- | --- |
| `README.md` | Projektbeschreibung und Dokumentation |
| `nasa_stars_data.csv` | Originaldatensatz |
| `star_type_classification.ipynb` | Jupyter Notebook mit Analyse, Cleaning, Modellierung und Bericht |
| `requirements.txt` | Benoetigte Python-Pakete |
| `GA_Nasa_Abgabe ZIP.zip` | ZIP-Datei fuer die Abgabe |

## Installation 
(das haben wir hier mal aufgeschireben dass wir es einfach kopieren könne, geht shcneller als das immer einzutippen)

Zuerst in den Projektordner wechseln:

```bash
cd "/Users/danakando/MCI/sem 2/data science /GA Nasa_Stars"
```

Dann die benoetigten Pakete installieren:

```bash
python3 -m pip install -r requirements.txt
```

### Notebook starten
Nach der Installation kann das Notebook mit Jupyter geöffnet werden:

```bash
jupyter notebook
```

Danach die Datei `star_type_classification.ipynb` auswählen und die Zellen der Reihe nach ausführen.

### Reproduzierbarkeit
Alle wesentlichen Schritte sind im Notebook dokumentiert:

1. Laden des Datensatzes
2. Erste Exploration
3. Analyse von Datenproblemen
4. Datenbereinigung
5. Aufbau der Preprocessing-Pipeline
6. Training und Vergleich mehrerer Modelle
7. Evaluation des finalen Modells
8. Schriftliche Zusammenfassung und Reflexion



## Einsatz von KI
Wir haben ChatGPT als Unterstützung für dieses Projekt verwendet. Die KI hat uns vor allem geholfen, das Notebook besser zu strukturieren, Formulierungen zu überarbeiten und technische Fehler schneller zu finden.

Genutzt wurde ChatGPT unter anderem für:
- Vorschläge zur Gliederung des Notebooks
- Hilfe bei der Beschreibung der Datenprobleme
- Unterstützung beim Laden und Bereinigen der CSV-Datei
- Vorschläge für eine passende Machine-Learning-Pipeline
- Hilfe beim Debugging, insbesondere bei leeren Zeilen ohne Zielvariable
- Überarbeitung der README-Datei und Hinweise zur Abgabe-ZIP

Die Ergebnisse wurden von uns geprüft und angepasst. Die finale Verantwortung für den Code, die Interpretation der Ergebnisse und die Abgabe liegt bei unserer Gruppe.

