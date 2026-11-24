# AGENTS.md — [Projektname]

<!-- Startervorlage: Platzhalter ersetzen, Unbekanntes als offen markieren und vor dem Einsatz gemeinsam prüfen. Als AGENTS.md im Repository-Hauptverzeichnis speichern. -->

## Product Context
- Zweck, Nutzer und gewünschte Verbesserung: [kurz beschreiben]
- Grundprinzipien und bewusste Grenzen: [benennen]
- Führende Anforderungen / bestätigte Spec und menschlicher Owner: [Pfad oder Link; Person]

## Architecture
- Technologien, Verzeichnisse und relevante Einstiegspunkte: [nur belegte Angaben]
- Code-, Design- und Sprachkonventionen: [bestehende Referenzen]
- Schnittstellen und unveränderliche Vorgaben: [benennen]
- Fehlende Angaben: [offen + zuständige Person; nichts erfinden]

## Agent Rules
- Vor Änderungen die bestätigte Anforderung und die relevanten Projektdateien lesen. Nur den für den Auftrag nötigen Kontext verwenden.
- Kleine, zusammenhängende Änderungen umsetzen; vorhandene Komponenten nutzen. Keine neuen Abhängigkeiten oder Erweiterung des Auftrags ohne vereinbarte Entscheidung.
- Erlaubte Aktionen, Budget und Stoppregeln: [konkret festlegen]. Diese Datei erteilt keine zusätzlichen Rechte.
- Bei risikoarmen Lücken die kleinste reversible Lösung wählen und Annahmen festhalten. Kritische Unklarheiten, Widersprüche oder nötige Umfangsänderungen mit [Owner] vor der betroffenen Umsetzung klären.
- Keine Zugangsdaten, vertraulichen Daten oder erfundenen Prüfergebnisse einfügen. Prüfkriterien nicht eigenmächtig abschwächen.

## Quality Gates
- Definition of Ready: Anforderung, Umfang, Beispiele, Owner und relevanter Projektkontext sind geklärt; betroffene Kontextdateien sind geprüft und bei Bedarf aktualisiert.
- Relevante Prüfungen und Befehle: [bestehende Tests, Build und weitere Checks mit Arbeitsverzeichnis; unbekannte Befehle als offen markieren]. Prüftiefe am Risiko ausrichten.
- Definition of Done: vereinbarte Kriterien erfüllt, betroffene Dokumentation aktualisiert und Ergebnisse nachgewiesen. Nicht ausgeführte Checks und offene Befunde ausdrücklich nennen.
- Review und Freigabe: [bestehenden Ablauf und menschliche Entscheidungsrechte eintragen]. Automatische Checks und Agentenbefunde unterstützen die Prüfung; sie ersetzen keine menschliche Entscheidung. Blockierende Befunde beheben und erneut prüfen; relevante Änderungen nach Freigabe erneut vorlegen.

## Documentation
- Bei Änderungen alle betroffenen .md-Dateien mitführen, z. B. README.md, Architekturhinweise und diese AGENTS.md. Falls keine Anpassung nötig ist, kurz begründen.
- Dokumentation, Code, Spec-Version und vorhandene Sprachversionen konsistent halten. Generierte Dateien an ihrer Quelle aktualisieren: [Quellen und Exportbefehle].

## Feedback & Learning
- Beobachtungen und Evidence können bessere Anforderungen, Prozesse und Agentenregeln begründen.
- Änderungsvorschläge mit Anlass, Geltungsbereich, Owner und Prüfpunkt festhalten. Ungewisse Regeln begrenzt erproben; [zuständige Person] entscheidet über die Übernahme.
- Bestätigte Regeln versionieren, beim nächsten Auftrag berücksichtigen und auf Nutzen prüfen; überholte Regeln entfernen. Ein einzelner Fehler ist noch kein Naturgesetz.
