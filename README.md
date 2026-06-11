# Star Type Classification - NASA Stars

Gruppenarbeit im 2. Semester des Data-Science-Kurses.

## Gruppenmitglieder

- Mona Auer
- Leni Biasi
- Dana Kando

## Projektbeschreibung

In diesem Projekt wird das **Star Type Classification Dataset** analysiert. Ziel ist es, anhand physikalischer und spektraler Merkmale vorherzusagen, zu welcher Sternklasse ein Objekt gehoert.

Die Zielvariable ist `Type`. Sie beschreibt sechs verschiedene Sternklassen:

| Type | Sternklasse |
| --- | --- |
| 0 | Red Dwarf |
| 1 | Brown Dwarf |
| 2 | White Dwarf |
| 3 | Main Sequence |
| 4 | Super Giants |
| 5 | Hyper Giants |

Das Projekt umfasst das Laden, Explorieren, Bereinigen und Modellieren des Datensatzes. Die finale Machine-Learning-Pipeline befindet sich im Jupyter Notebook.

## Datensatz

Die Datei `nasa_stars_data.csv` enthaelt 240 Beobachtungen mit folgenden Merkmalen:

| Spalte | Beschreibung |
| --- | --- |
| `Temperature` | Oberflaechentemperatur des Sterns in Kelvin |
| `L` | Relative Leuchtkraft im Vergleich zur Sonne |
| `R` | Relativer Radius im Vergleich zur Sonne |
| `A_M` | Absolute Magnitude / intrinsische Helligkeit |
| `Color` | Beobachtete Farbe des Sterns |
| `Spectral_Class` | Spektralklasse nach dem Harvard-System |
| `Type` | Zielvariable fuer die Sternklasse |

Beim Laden der Datei mussten einige Besonderheiten beruecksichtigt werden:

- Die Datei verwendet `~` als Trennzeichen.
- Vor der eigentlichen Kopfzeile steht eine Beschreibungszeile.
- Rechts neben den relevanten Spalten befinden sich leere Zusatzspalten.
- Es gibt fehlende Werte in mehreren Spalten.
- Die Spalte `Color` enthaelt uneinheitliche Schreibweisen und einzelne Tippfehler.

Die Originaldatei wurde nicht manuell veraendert. Alle Bereinigungsschritte sind im Notebook nachvollziehbar dokumentiert.

## Machine-Learning-Ansatz

Das Projekt wurde als ueberwachtes Klassifikationsproblem umgesetzt.

Verwendete Features:

- Numerische Features: `Temperature`, `L`, `R`, `A_M`
- Kategoriale Features: `Color`, `Spectral_Class`

Die Preprocessing-Pipeline umfasst:

- Umwandlung numerischer Spalten
- Vereinheitlichung von Farbkategorien
- Behandlung fehlender Werte
- Skalierung numerischer Variablen
- One-Hot-Encoding kategorialer Variablen

Anschliessend wurden mehrere Klassifikationsmodelle verglichen, unter anderem:

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
| `GA_Nasa_submission.zip` | ZIP-Datei fuer die Abgabe |

## Installation

Zuerst in den Projektordner wechseln:

```bash
cd "/Users/danakando/MCI/sem 2/data science /GA Nasa KI komplett"
```

Dann die benoetigten Pakete installieren:

```bash
python3 -m pip install -r requirements.txt
```

## Notebook starten

Nach der Installation kann das Notebook mit Jupyter geoeffnet werden:

```bash
jupyter notebook
```

Danach die Datei `star_type_classification.ipynb` auswaehlen und die Zellen der Reihe nach ausfuehren.

## Reproduzierbarkeit

Alle wesentlichen Schritte sind im Notebook dokumentiert:

1. Laden des Datensatzes
2. Erste Exploration
3. Analyse von Datenproblemen
4. Datenbereinigung
5. Aufbau der Preprocessing-Pipeline
6. Training und Vergleich mehrerer Modelle
7. Evaluation des finalen Modells
8. Schriftliche Zusammenfassung und Reflexion

## Einsatz von LLMs

Fuer dieses Projekt wurde ein Large Language Model als Unterstuetzung verwendet. Es wurde genutzt fuer:

- Strukturierung des Notebooks
- Formulierung von Dokumentationstexten
- Entwicklung einer sinnvollen Machine-Learning-Strategie
- Hinweise zur Datenbereinigung und Pipeline-Struktur

Die finale Verantwortung fuer Code, Ergebnisse und Interpretation liegt bei der Gruppe. Alle Gruppenmitglieder muessen die Arbeitsschritte nachvollziehen und erklaeren koennen.
