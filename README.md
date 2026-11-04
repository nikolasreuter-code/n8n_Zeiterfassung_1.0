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
