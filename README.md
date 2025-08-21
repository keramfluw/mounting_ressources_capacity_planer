# Installer Economics – v2

Interaktive Streamlit-App zur Wochenplanung und Wirtschaftlichkeitsanalyse
für Montage-Teams. Enthält:
- **Gerätekatalog** mit editierbaren **Montagezeiten** & **Vergütungen**
- **CSV-Import/Export & Persistenz** der Raten unter `assets/zaehler_parameter.csv`
- **Mix (Projekt→Gerät)** je Kategorie
- **Projektpipeline** mit Summen je Kategorie
- **Auto-Planer** (max. Umsatz pro Stunde unter Kapazitätsgrenzen)
- **KPIs & Visualisierung**
- **Excel-Export** aller Eingaben und Ergebnisse

## Quickstart (lokal)

```bash
python3.11 -m venv .venv && source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
streamlit run app.py
```

> Hinweis: Das Paket setzt standardmäßig auf **Python 3.11** (stabilste Wheels).

## Streamlit Cloud (Deployment)

1. Repo verbinden und deployen.
2. In den App-Einstellungen die **Python-Version 3.11** wählen.
3. Bei Bedarf `assets/zaehler_parameter.csv` im Repo anpassen/ergänzen.
4. Änderungen committen → Rebuild → App starten.

## Python 3.13 (optional)

Wenn das Zielsystem zwingend Python **3.13** nutzt, heben Sie die
Abhängigkeiten an (Wheels für cp313). Ersetzen Sie `requirements.txt` durch:

```
streamlit==1.48.0
numpy>=2.1
pandas>=2.2.3
matplotlib>=3.9
xlsxwriter>=3.1
```

## Datenpersistenz

- Die editierten Raten werden auf Wunsch über den Button **„Als Standard speichern“**
  in `assets/zaehler_parameter.csv` persistiert.
- Beim Start lädt die App automatisch diese CSV (Fallback: interne Defaults).

## Struktur

- `app.py` – Streamlit-App
- `requirements.txt` – Abhängigkeiten (Pin-Set für Python 3.11)
- `assets/zaehler_parameter.csv` – Defaults für Geräte/Zeiten/Preise (frei editierbar)

## Lizenz

Interner Projekt-Use. Keine Gewähr.
