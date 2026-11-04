# n8n_Zeiterfassung_1.0
KI-gestützte Zeiterfassung über Telegram mit n8n, OpenAI und Google Sheets. Erweiterung um menschliche Freigabe (Human Oversight).
# KI-gestützte Zeiterfassung mit Telegram und n8n

## 1. Projektbeschreibung

Dieser Workflow soll die Arbeitszeiterfassung vereinfachen. Mitarbeiter können ihre Arbeitszeiten per Telegram-Sprachnachricht übermitteln.

Die Sprachnachricht wird mithilfe von KI in Text umgewandelt und ausgewertet. Anschließend werden die erkannten Arbeitszeiten geprüft und bei vollständigen Angaben in Google Sheets gespeichert.

## 2. Ziel und Nutzen

- Einfachere Erfassung von Arbeitszeiten
- Weniger manuelle Eingaben
- Automatische Berechnung der Arbeitszeit
- Rückfragen bei fehlenden Angaben
- Zentrale Dokumentation in Google Sheets

## 3. Verwendete Technologien

- **n8n:** Automatisierung des Workflows
- **Telegram:** Übermittlung von Sprachnachrichten und Rückmeldungen
- **OpenAI:** Transkription und Auswertung der Arbeitszeiten
- **Google Sheets:** Speicherung der erfassten Arbeitszeiten
- **Docker:** Lokaler Betrieb von n8n
- **Cloudflare Tunnel:** Bereitstellung einer öffentlichen HTTPS-Adresse für den Telegram Trigger

## 4. Bestehender Workflow – Version 1.0

1. Eine Sprachnachricht wird über Telegram empfangen.
2. Der Workflow prüft, ob eine Sprachnachricht vorliegt.
3. Die Audiodatei wird über Telegram abgerufen.
4. OpenAI soll die Sprache in Text umwandeln.
5. Die KI soll Datum, Arbeitsbeginn, Arbeitsende und Pausen erkennen.
6. Die Angaben werden geprüft und die Arbeitszeit berechnet.
7. Bei vollständigen Angaben sollen die Daten in Google Sheets gespeichert werden.
8. Der Nutzer erhält eine Bestätigung oder eine Rückfrage.

**Aktueller Stand:** Der Workflow wurde erstellt und in GitHub gesichert. Die vollständige Funktionsprüfung steht noch aus. Insbesondere die Telegram-Verbindung, die OpenAI-Transkription und Google Sheets müssen getestet werden.

## 5. Geplante Erweiterung – Human Oversight

Der Workflow soll um eine menschliche Freigabe erweitert werden.

Bevor die erkannten Arbeitszeiten in Google Sheets gespeichert werden, erhält der Nutzer eine Zusammenfassung über Telegram.

Der Nutzer kann die Angaben bestätigen oder eine Korrektur veranlassen.

**Erst nach ausdrücklicher Bestätigung sollen die Daten gespeichert werden.**

Dadurch sollen fehlerhafte Zeiteinträge vermieden und die Kontrolle durch den Menschen sichergestellt werden.

## 6. Datenschutz und Risiken

Arbeitszeiten und Telegram-Nutzerkennungen können personenbezogene Daten sein.

Deshalb müssen insbesondere folgende Punkte berücksichtigt werden:

- Nur notwendige Daten verarbeiten.
- Zugangsdaten und API-Schlüssel sicher aufbewahren.
- Zugriffsrechte auf Google Sheets begrenzen.
- Nutzer über die Datenverarbeitung informieren.
- Löschfristen und Aufbewahrungspflichten klären.
- Fehlerhafte KI-Ergebnisse durch menschliche Kontrolle abfangen.

Vor einem echten Unternehmenseinsatz sind die datenschutzrechtlichen und organisatorischen Anforderungen gesondert zu prüfen.

## 7. Nächste Schritte

- Telegram Trigger und HTTPS-Verbindung testen
- OpenAI und Google Sheets konfigurieren
- Bestehenden Workflow vollständig testen
- Menschliche Freigabe ergänzen
- Fehlerbehandlung und Tests dokumentieren
- Abschließende Bewertung der Erweiterung erstellen

## 8. Projektstatus

**Version:** 1.0 – Ausgangszustand

**Status:** In Entwicklung, noch nicht vollständig getestet

**Geplante Erweiterung:** Menschliche Freigabe vor Speicherung der Arbeitszeiten

---

## 8. Technische und organisatorische Einbindung

### Technische Umsetzung

Der Workflow wird mit n8n erstellt und automatisiert die Erfassung von Arbeitszeiten über Telegram.

Folgende Systeme werden miteinander verbunden:

- **Telegram:** Mitarbeiter übermitteln ihre Arbeitszeiten als Sprachnachricht.
- **n8n:** Steuert die einzelnen Arbeitsschritte und verbindet die Systeme.
- **OpenAI:** Wandelt Sprachnachrichten in Text um und erkennt die relevanten Arbeitszeitangaben.
- **Google Sheets:** Speichert die geprüften Arbeitszeiten.
- **Docker:** Stellt die lokale n8n-Umgebung bereit.
- **Cloudflare Tunnel:** Ermöglicht eine öffentliche HTTPS-Verbindung für den Telegram Trigger.

Der Workflow befindet sich aktuell in einer lokalen Entwicklungsumgebung. Für einen dauerhaften Unternehmenseinsatz wäre eine zuverlässig erreichbare und abgesicherte Serverumgebung erforderlich.

### Organisatorische Einbindung

In einem Unternehmen müssten klare Verantwortlichkeiten festgelegt werden:

- **Mitarbeiter:** Übermitteln und bestätigen ihre eigenen Arbeitszeiten.
- **Personalabteilung:** Kontrolliert die erfassten Daten und bearbeitet Unstimmigkeiten.
- **IT-Abteilung:** Betreut n8n, die Schnittstellen und die technischen Zugänge.
- **Datenschutzbeauftragte:** Prüfen die datenschutzrechtlichen Anforderungen, soweit eine entsprechende Funktion vorhanden ist.
- **Unternehmensleitung:** Entscheidet über die Einführung und legt interne Regeln fest.

Vor der Einführung sollte der Workflow zunächst mit Testdaten erprobt werden.

## 9. Governance und Compliance

Damit der Workflow in einem Unternehmen eingesetzt werden kann, müssen rechtliche und interne Vorgaben berücksichtigt werden.

### Datenschutz (DSGVO)

Arbeitszeiten und Telegram-Nutzerkennungen sind personenbezogene Daten.

Deshalb gelten insbesondere folgende Grundsätze:

- **Datenminimierung:** Es werden nur die Daten verarbeitet, die für die Zeiterfassung erforderlich sind.
- **Zweckbindung:** Die Daten werden ausschließlich für den festgelegten Zweck verwendet.
- **Zugriffsschutz:** Nur berechtigte Personen dürfen Arbeitszeitdaten einsehen oder bearbeiten.
- **Transparenz:** Mitarbeiter müssen über die Verarbeitung ihrer Daten informiert werden.
- **Speicherung und Löschung:** Aufbewahrungsfristen und Löschregeln müssen festgelegt werden.
- **Technische und organisatorische Maßnahmen (TOMs):** Beispielsweise Zugriffsbeschränkungen, sichere Zugangsdaten und geschützte Verbindungen.

Vor einem produktiven Einsatz müssen außerdem die Rechtsgrundlage, die beteiligten Dienstleister und mögliche Datenübermittlungen in Drittländer geprüft werden. Dazu gehören insbesondere Telegram, OpenAI und Google.

### EU AI Act

Die KI unterstützt bei der Transkription und Auswertung von Arbeitszeiten.

Die Ergebnisse dürfen nicht ungeprüft als richtig angenommen werden.

Deshalb wird eine menschliche Freigabe vorgesehen.

Vor einem Unternehmenseinsatz muss außerdem geprüft werden, welche Anforderungen des EU AI Act für den konkreten Anwendungsfall gelten. Die Risikoeinstufung hängt insbesondere davon ab, wie die KI-Ergebnisse verwendet werden.

### Urheberrecht

Der Workflow wird für ein eigenes Projekt entwickelt. Bei der Verwendung fremder Vorlagen, Texte oder Programmteile müssen die jeweiligen Nutzungsrechte und Lizenzen berücksichtigt werden.

### Mitbestimmung

Bei einem Einsatz zur Mitarbeiter-Zeiterfassung können Mitbestimmungsrechte des Betriebsrats relevant sein, insbesondere wenn das System zur Überwachung von Verhalten oder Leistung geeignet ist.

Eine Einführung müsste deshalb gegebenenfalls mit dem Betriebsrat abgestimmt werden.

### Interne Unternehmensregeln

Zusätzlich müssen interne IT-Sicherheitsrichtlinien, Berechtigungskonzepte und Freigabeprozesse eingehalten werden.

## 10. Risiken und Gegenmaßnahmen

| Risiko | Mögliche Gegenmaßnahme |
|---|---|
| KI erkennt falsche Arbeitszeiten | Menschliche Bestätigung vor Speicherung |
| Sprachnachricht ist unverständlich | Rückfrage an den Nutzer |
| Angaben sind unvollständig | Fehlende Informationen gezielt abfragen |
| Unberechtigter Zugriff | Berechtigungen und zugelassene Telegram-Nutzer prüfen |
| Personenbezogene Daten werden ungeschützt verarbeitet | Datenminimierung, Zugriffsschutz und sichere Übertragung |
| Telegram oder OpenAI ist nicht erreichbar | Fehlermeldung und Möglichkeit zur späteren erneuten Eingabe |
| Arbeitszeit wird doppelt gespeichert | Prüfung auf bereits verarbeitete Nachrichten |
| Fehler beim Speichern in Google Sheets | Fehlerprotokoll und Benachrichtigung |
| Cloudflare-Tunnel oder lokaler Server fällt aus | Für den Produktivbetrieb eine stabile Serverlösung verwenden |

Die Gegenmaßnahmen sind teilweise noch geplant und müssen bei der praktischen Umsetzung berücksichtigt werden.

## 11. Human Oversight – Menschliche Kontrolle

### Geplante Erweiterung

Der bestehende Workflow soll um eine menschliche Freigabe ergänzt werden.

Bisher sieht der Workflow vor, vollständige Arbeitszeitangaben automatisch in Google Sheets zu speichern.

Künftig soll vor der Speicherung eine Bestätigung durch den Nutzer erfolgen.

### Geplanter Ablauf

1. Der Mitarbeiter sendet eine Telegram-Sprachnachricht.
2. Die KI wandelt die Sprache in Text um.
3. Die KI erkennt Datum, Arbeitsbeginn, Arbeitsende und Pause.
4. n8n prüft die Angaben und berechnet die Arbeitszeit.
5. Der Mitarbeiter erhält eine Zusammenfassung über Telegram.
6. Der Mitarbeiter kann die Angaben bestätigen oder eine Korrektur anfordern.
7. Erst nach der Bestätigung werden die Arbeitszeiten in Google Sheets gespeichert.
8. Bei einer Korrektur werden die Angaben erneut geprüft.

### Beispiel

Ein Mitarbeiter sagt:

„Ich habe heute von 8 bis 16 Uhr gearbeitet und 30 Minuten Pause gemacht.“

Die KI erkennt:

- Beginn: 08:00 Uhr
- Ende: 16:00 Uhr
- Pause: 30 Minuten
- Arbeitszeit: 7,5 Stunden

Der Mitarbeiter erhält anschließend eine Nachricht mit diesen Angaben und kann sie bestätigen oder korrigieren.

### Nutzen der menschlichen Kontrolle

Die KI übernimmt die Vorbereitung und Berechnung. Die endgültige Freigabe bleibt beim Menschen.

Dadurch sollen Fehler reduziert und die Nachvollziehbarkeit verbessert werden.

**Umsetzungsstand:** Die Erweiterung ist konzipiert, aber noch nicht technisch eingebaut und getestet.

## 12. Test
