# Data Analyse Project
# 📊 Online-Retail Datenanalyse & AWS Cloud Integration

Dieses Projekt zeigt einen vollständigen **Data Engineering & Science Workflow**. Es umfasst den gesamten Prozess von der Extraktion der Rohdaten aus der **AWS S3 Cloud** über eine intensive Bereinigung bis hin zur fortgeschrittenen Kunden-Segmentierung mittels RFM-Analyse.

---

## 🚀 Projektübersicht
Das Hauptziel dieses Projekts ist die Verarbeitung eines umfangreichen Datensatzes aus dem Online-Einzelhandel. Dabei wurden technische Hürden wie fehlende Werte und inkonsistente Datentypen überwunden, um fundierte betriebswirtschaftliche Erkenntnisse zu gewinnen.

## 🛠 Technologien & Tools
*   **Python:** Kernsprache für die Analyse.
*   **Pandas:** Zur effizienten Datenmanipulation.
*   **Boto3:** Für die direkte Kommunikation mit **Amazon Web Services (AWS)**.
*   **Matplotlib & Seaborn:** Zur Erstellung der Datenvisualisierungen.
*   **RFM-Analyse:** Ein Modell zur Bewertung des Kundenwerts.

---

## ⚙️ Workflow & Funktionen

### 1. Cloud-Datenextraktion
Das Skript verbindet sich sicher mit einem **S3 Bucket**. Unter Verwendung von AWS-Zugangsdaten werden die Rohdaten (`Online Retail.xlsx`) direkt in die Umgebung geladen.

### 2. Datenbereinigung (Data Cleaning)
Rohdaten sind oft unvollständig. In diesem Schritt haben wir:
*   Zeilen ohne `CustomerID` oder `Description` entfernt.
*   Ungültige Transaktionen mit Mengen oder Preisen von Null oder weniger gefiltert.
*   Das `InvoiceDate` in ein einheitliches Datetime-Objekt konvertiert.

### 3. Fehlerbehebung & Typkonvertierung
Ein besonderes Augenmerk lag auf der Konsistenz der Datentypen. Spalten wie `StockCode`, die gemischte Typen enthielten, wurden explizit in Strings umgewandelt, um Fehler beim Export in das **Parquet-Format** zu vermeiden.

### 4. Datenspeicherung & Backup
Die bereinigten Daten werden in zwei Formaten zurück in die Cloud hochgeladen:
*   **Parquet:** Optimiert für schnelle Verarbeitung.
*   **Excel:** Für die einfache Einsicht durch das Management.

---

## 📈 Visualisierungen & Insights

| Analyse | Beschreibung |
| :--- | :--- |
| **Top 10 Länder** | Identifikation der stärksten Märkte nach Gesamtumsatz. |
| **Bestseller** | Analyse der 10 meistverkauften Produkte zur Lageroptimierung. |
| **Umsatzentwicklung** | Zeitreihenanalyse zur Identifikation von monatlichen Trends. |

---

## 🎯 RFM-Kunden-Segmentierung
Um den Kundenstamm besser zu verstehen, wurde eine **RFM-Analyse** implementiert:
*   **Recency (Aktualität):** Tage seit dem letzten Kauf.
*   **Frequency (Häufigkeit):** Anzahl der getätigten Käufe.
*   **Monetary (Umsatz):** Gesamtwert der Ausgaben des Kunden.

> [!TIP]
> **Sicherheitshinweis:** Beim Ausführen des Notebooks werden die AWS-Zugangsschlüssel sicher über die `getpass`-Funktion abgefragt. Dies stellt sicher, dass keine sensiblen Anmeldedaten im Quellcode gespeichert werden.

---
**Datenquelle:** Online Retail Dataset - `ana1.ipynb`
