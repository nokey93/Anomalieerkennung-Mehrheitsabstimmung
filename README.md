Dieses Repository demonstriert eine Vorgehensweise zur Erkennung von Anomalien in Brauereidaten. Ziel ist es, Messwerte (z.\u00a0B. Druck oder Temperatur) mithilfe mehrerer Verfahren zu pr\u00fcfen und die einzelnen Ergebnisse \u00fcber eine Mehrheitsabstimmung zusammenzuf\u00fchren.

## Datenbasis
Die Notebookbeispiele verwenden CSV-Dateien, die Zeitstempel und Messreihen enthalten. Diese Daten werden im Notebook direkt eingelesen. Eigene Dateien k\u00f6nnen \u00fcber den Pfad in der zweiten Zelle eingebunden werden.

## Eingesetzte Verfahren
Vier verschiedene Methoden zur Anomalieerkennung werden kombiniert:

1. **Facebook Prophet** zur Vorhersage des Trends und Bestimmung von Konfidenzintervallen.
2. **Drei-Sigma-Regel** (Berechnung des erwarteten Wertebereichs \u00fcber Mittelwert und Standardabweichung).
3. **Einfacher gleitender Durchschnitt (SMA)** mit Bollinger\u2013\u00e4hnlichen B\u00e4ndern.
4. **Exponentieller gleitender Durchschnitt (EMA)** mit vergleichbaren B\u00e4ndern.

Jede Methode kennzeichnet Messpunkte als \u201eAnomalie\u201c oder \u201eNormalfall\u201c. Anschlie\u00dfend wird pro Zeitstempel gez\u00e4hlt, wie viele Verfahren eine Anomalie erkannt haben. \u00dcberschreitet dieser Anteil ein vorgegebenes Quorum (im Notebook 50\u00a0%), wird der Punkt endg\u00fcltig als Anomalie markiert.

## Nutzung
Das gesamte Vorgehen ist im Notebook `Anomlie_Voting_v1.ipynb` nachvollziehbar. Zur Ausf\u00fchrung wird eine Python-Umgebung mit den dort importierten Bibliotheken ben\u00f6tigt (u.\u00a0a. `pandas`, `numpy`, `fbprophet`, `seaborn`). Die Ergebnisse werden grafisch dargestellt und k\u00f6nnen optional als CSV gespeichert werden.

1. Notebook \u00f6ffnen und die Datenquelle in Zelle&nbsp;2 anpassen.
2. Alle Zellen ausf\u00fchren, um die Zwischenergebnisse der einzelnen Methoden zu erzeugen.
3. Die finale Tabelle `anomaly_tmp` enth\u00e4lt f\u00fcr jede Messung die Anzahl der positiven Stimmen und den Abstimmungsprozentsatz.

## Dateien
* `Anomlie_Voting_v1.ipynb` – Schrittweise Analyse und Mehrheitsabstimmung
* `Anomalieerkennung_bei_Brauereidaten_Ver_2.pdf` – begleitende Ausarbeitung

Diese vereinfachte Implementierung dient als Anschauungsbeispiel. Sie kann f\u00fcr eigene Datens\u00e4tze angepasst und erweitert werden.
