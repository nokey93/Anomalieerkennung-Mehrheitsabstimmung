## Optimierung der Anomalieerkennung in Brauereidaten mithilfe von Mehrheitsabstimmung

Dieses Projekt demonstriert ein Verfahren zur Detektion von Ausreißern in Prozessdaten einer Brauerei. Mehrere Algorithmen werden parallel ausgeführt und ihre Ergebnisse über ein Mehrheitsvotum zusammengeführt. Ziel ist es, die Erkennungsgenauigkeit gegenüber Einzelverfahren zu erhöhen.

## Verwendete Algorithmen

* **Facebook Prophet** zur Prognose und zum Vergleich der tatsächlichen Messwerte mit den Vorhersageintervallen
* **Drei-Sigma-Regel** (Mean ± 3  σ) zur einfachen Ausreißerdetektion
* **Simple Moving Average (SMA)** mit konfigurierbarem Fenster
* **Exponential Moving Average (EMA)** als gewichteter gleitender Durchschnitt

Jeder Algorithmus kennzeichnet Datenpunkte als „Anomalie“ oder „Normalfall“. In einem anschließenden Schritt wird für jeden Zeitpunkt gezählt, wie viele Verfahren eine Anomalie melden. Liegt der Anteil über einem festgelegten Schwellwert, wird der Datenpunkt als Anomalie klassifiziert.

## Ausführen des Notebooks

1. Python 3 sowie die benötigten Bibliotheken installieren, zum Beispiel
   ```bash
   pip install numpy pandas holoviews matplotlib altair seaborn fbprophet
   ```
2. Das Notebook `Anomlie_Voting_v1.ipynb` in Jupyter öffnen.
3. Pfad zum Datensatz anpassen (z.B. `D:\THOWL\Anwendungsprojekt\Daten\2022_06_15\filt_1.csv`).
4. Alle Zellen ausführen, um die Detektion und die Mehrheitsabstimmung durchzuführen.

Die Ergebnisse werden als Tabellen und Diagramme im Notebook ausgegeben. Auffällige Zeitpunkte können optional in einer CSV-Datei gespeichert werden.
