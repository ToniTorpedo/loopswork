CART 1.0 – vollständige Muster-Spec

Einordnung und Versionsstand
SPEC CART · Version 1.0 · Referenzfassung des LoopsWork-Lernbeispiels
Diese vollständig ausgefüllte Muster-Spec beschreibt die bereits gezeigten Warenkorbregeln. Rollen, Budget und Messplan sind illustrative Annahmen. Sie ist keine reale Produktfreigabe und kein Nachweis einer produktiven Implementierung.
Führende Beispielquelle: https://loopswork.dev/docs/#cart-spec
Owner: Product Owner Onlineshop (Beispielrolle). Fachliche Bestätigung: Feature Partner und PO; technische Vereinbarung: Delivery Team; Messplan: Measurement Partner.
Im Lernablauf gilt CART 1.0 ab Abschluss von B3 als bestätigt. Ein reales Bestätigungsdatum und ein unveränderlicher Git-Commit bzw. eine Dokumentrevision müssen bei der Übernahme ins eigene Projekt ergänzt werden. Die Website-URL allein ersetzt diesen festen Stand nicht.

1. Problem und Zielgruppe
Illustrativer Auftrag: Die Bereichsleitung verantwortet die strategische Initiative „Einkauf vereinfachen“ und beauftragt den PO mit dem Warenkorb-Beitrag. Das ist eine ergänzende Beispielannahme. Der PO priorisiert den konkreten Umfang im beauftragten Rahmen; technische Umsetzung und Arbeitsteilung liegen beim Team. Änderungen am übergeordneten Ziel oder Budget gehen an die Bereichsleitung.
Kunden mit einer Artikelauswahl sollen vor dem Checkout Mengen korrigieren, Artikel entfernen und den Gesamtpreis verstehen können. Die Beispielannahme lautet: Umständliche Korrekturen und unklare Versandkosten erschweren den Checkout-Beginn. Reale Nutzerbelege sind in dieser Lerndemo nicht vorhanden; im Projekt prüft der Fachpartner die Annahme mit Nutzertests und Feedback.

2. Erwarteter Nutzen und Investitionsrahmen
Hypothese: Wenn Kunden Mengen einfach ändern und den Gesamtpreis verstehen, beginnen mehr geeignete Sitzungen mit gefülltem Warenkorb den Checkout.
Beispiel-Ausgangswert: 58 %. Beispielziel: mindestens 62 % bei eingehaltenen Schutzgrenzen. Diese Zahlen sind erfundene Annahmen, keine Messwerte der Website.
Für die erste Änderung: höchstens 5 Teamarbeitstage und 50 € KI-Kosten. Prüfpunkt bei halbem Verbrauch. Teamaufwand ist nicht Kalenderdauer. Im Muster ist dem PO die Entscheidung über Fortsetzung, Verkleinerung oder Stopp innerhalb dieses Rahmens übertragen. Ein größeres Budget oder ein geändertes strategisches Ziel bestätigt die zuständige Bereichsleitung.

3. Umfang und bewusste Grenzen
Enthalten: Artikel hinzufügen, Mengen ändern, Positionen entfernen, Artikelwert und Versandkosten berechnen, Gesamtpreis anzeigen und leeren Checkout verhindern.
Nicht enthalten: Rabattcodes, Merkliste, Gastkonto-Synchronisierung, Zahlung und echte Bestellabwicklung.
Die Website bildet die Regeln lokal im Browser ab. Ein produktiver Warenkorb benötigt zusätzlich serverseitige Prüfungen, Zugriffsschutz, Betrieb und Freigaben. Die unten beschriebenen Anforderungen an einen echten Service sind nicht als vorhandene Website-Funktionen zu verstehen.

4. Vereinbarte Regeln und Akzeptanzkriterien
AK-01 · Hinzufügen: Ein vorhandener Artikel wird nicht als zweite Position angelegt. Gegeben Kaffee mit Menge 1, wenn derselbe Artikel erneut hinzugefügt wird, dann besteht eine Position mit Menge 2.
AK-02 · Mengen: Zulässig sind ganze, nichtnegative Mengen. Menge 0 entfernt die Position. Negative und gebrochene Mengen werden abgewiesen; der bisherige Warenkorb bleibt unverändert.
AK-03 · Bestand: Die gewünschte Menge darf den verfügbaren Bestand nicht überschreiten. Bei Bestand 5 wird Menge 6 abgewiesen und der Warenkorb nicht verändert. Menge 5 ist zulässig.
AK-04 · Geld und Summen: Geld wird in ganzzahligen Cent berechnet. Artikelwert ist die Summe aus Menge × gültigem Einzelpreis. Gesamtpreis ist Artikelwert plus Versand. Nach erfolgreichem Hinzufügen, Ändern oder Entfernen werden die angezeigten Summen aktualisiert. Im echten Service sind serverseitige Preise maßgeblich. Beispiel: 2 × 1.490 Cent + 490 Cent Versand = 3.470 Cent.
AK-05 · Versand: Bei einem nichtleeren Warenkorb unter 5.000 Cent Artikelwert betragen die Versandkosten 490 Cent. Ab genau 5.000 Cent sind sie 0. Grenzfälle: 4.999 → 490 Cent Versand; 5.000 → 0. Nach einer Mengenänderung über oder unter die Grenze gilt sofort die neue Summe.
AK-06 · Leerzustand: Nach Entfernen des letzten Artikels sind Artikelwert, Versand und Gesamtpreis 0. Der Checkout ist gesperrt, der Leerzustand wird verständlich angezeigt.
Ungültige Aktionen zeigen eine verständliche Rückmeldung und verändern weder Positionen noch Summen. Die Bestandsgrenzen gelten auch beim wiederholten Hinzufügen.

5. Technischer Vertrag für eine echte Umsetzung
Entwurf: PUT /cart/items/{productId}
Body: { "quantity": 2 } setzt die gewünschte absolute Menge.
quantity: 0 entfernt die Position. Wiederholung derselben Setzoperation erhöht die Menge nicht zusätzlich; das Hinzufügen in der Oberfläche bestimmt die neue Zielmenge.
200: aktualisierter Warenkorb einschließlich serverseitiger Summen.
400: ungültige Menge. 404: unbekannter Artikel. 409: Bestand reicht nicht. Bei diesen Fehlern bleibt der Warenkorb unverändert.
Der Service prüft Eingaben, aktuellen Preis, Bestand und Berechtigung auf den betroffenen Warenkorb. Eine Bestellung und Reservierung von Bestand werden durch diesen Vertrag nicht ausgelöst.
Vor produktiver Umsetzung klärt das Team Authentifizierung, 401/403-Behandlung, parallele Änderungen, Transaktionsgrenzen und das konkrete Antwortschema. Diese offenen technischen Punkte sind kein stillschweigender Freiraum für Agenten. Sie blockieren den betroffenen Produktionsteil.

6. Tests, unabhängige Prüfung und Abnahme
Tests referenzieren CART 1.0 und die jeweiligen AK-IDs. Ein Prüfer arbeitet mit demselben festgelegten Spec-Stand wie der umsetzende Agent.
Automatisiert prüfen: wiederholtes Hinzufügen, Menge 0, negative und gebrochene Mengen, Bestand genau erreicht und überschritten, Cent-Berechnung, beide Seiten der Versandgrenze und leerer Checkout. Zustandswechsel prüfen: Nach jeder Aktion stimmen Positionen, Artikelwert, Versand und Gesamtpreis zusammen.
Für eine echte Umsetzung zusätzlich: Schnittstellenfehler, unberechtigter Zugriff, aktuelle serverseitige Preise und parallele Änderungen nach bestätigtem Vertrag.
Das Delivery Team erstellt Nachweise; ein menschlicher Reviewer prüft unabhängig. Der Feature Partner nimmt reale Einkaufsabläufe ab: Menge ändern, letzten Artikel entfernen, Bestand überschreiten und Versandgrenze wechseln. Abnahme protokolliert Spec-Stand, Code-Version, Prüffälle und Abweichungen. Schweigen ist keine Abnahme.
Die ausführbaren Website-Prüffälle sind Lernhilfen und ersetzen keine Serverintegration, Sicherheitsprüfung oder fachliche Abnahme.

7. Messplan und Produktentscheidung
Primäre Kennzahl: geeignete Sitzungen mit Checkout-Beginn geteilt durch geeignete Sitzungen mit gefülltem Warenkorb. Testverkehr ausschließen und wiederholte Ereignisse je Sitzung nur einmal zählen.
Messpunkte: erfolgreiche Mengenänderung, Warenkorbfehler und Beginn des Checkouts. Aktionen eindeutig zuordnen; keine personenbezogenen Freitexte erfassen.
Beispiel-Messfenster: Tag 6–18 nach Aktivierung an Tag 5, Vergleichsgruppe und neue Variante. Je 1.000 Sitzungen sind nur eine illustrative Auswertungsgröße. Messpartner klärt Gruppenbildung, Vergleichbarkeit und benötigte Datenmenge vorab.
Beispiel-Schutzgrenzen: Änderungsfehler höchstens 1 %, Ladezeit p95 höchstens 1,5 Sekunden. Preisbeschwerden und abgeschlossene Käufe zusätzlich beobachten; ihre Entscheidungsgrenzen müssen vor einem echten Experiment vereinbart werden.
Am Tag 20 prüft der PO mit Team und Partnern die Scorecard. Er entscheidet im delegierten Rahmen und gibt die Befunde an die beauftragende Bereichsleitung zurück; strategische Änderungen entscheidet diese. Fehlende Daten oder ungeklärte Vergleichbarkeit führen zu weiterer Untersuchung statt automatischer Ausweitung. Dringende schädliche Befunde werden sofort behandelt.
Die Scorecard mit fiktiven Ergebnissen steht unter https://loopswork.dev/docs/#scorecard. Die Website erhebt diese Shopdaten nicht.

8. Auslieferung, Betrieb und Rücknahme
Im Beispiel: Nach fachlicher Abnahme an Tag 5 nur mit vorliegenden Freigaben für eine begrenzte Nutzergruppe aktivieren. Das Release verknüpft CART 1.0, tatsächliche Code-Version, Testnachweise, Abnahme und Scorecard. Messdaten werden Release und Nutzergruppe zugeordnet.
Team und Freigabeverantwortlicher prüfen Fehlerrate, Preisrichtigkeit und Datenerfassung. Bei fehlerhaften Preisen oder schädlichen Befunden wird die Aktivierung gestoppt und der vereinbarte Rücknahmeweg genutzt. Die konkrete Umschaltung, zuständige Person und Behandlung bereits veränderter Daten müssen vor einem echten Release geklärt und erprobt sein.
Bei Rücknahme müssen Code, Konfiguration und zugehöriger Spec-Stand zusammenpassen.

9. Offene Fragen, Verantwortung und Versionierung
Vor echter Umsetzung offen: Nutzerbelege (Fachpartner), Authentifizierung und Parallelzugriffe (Team), Vergleichsdesign und Schutzgrenzen (Messpartner), Freigabe- und Rücknahmeweg (Team und Freigabeverantwortlicher). Frist jeweils vor Umsetzung bzw. Start des betroffenen Teils; konkrete Namen und Termine im Projekt zuordnen.
Version 1.0 dokumentiert die sechs bereits im Lernbeispiel vereinbarten Regeln. Diese ausgefüllte Fassung führt sie zusammen und erläutert ihre Anwendung; sie ändert die Versandgrenze nicht.
KI-Aufträge, Tests, Review und Abnahme nennen CART 1.0 plus festen Commit- oder Dokumentversionsverweis. Eine fachliche Änderung wird als neuer Entwurf mit Unterschied, Grund, betroffenen AK-IDs und menschlicher Bestätigung geprüft. Laufende Aufträge werden auf Auswirkungen geprüft.
Der auf der Beispielseite beschriebene Vorschlag CART 1.1 mit 6.000 Cent Versandgrenze ist hypothetisch und nicht Teil dieser Fassung. Bis zur ausdrücklichen Bestätigung einer neuen Vereinbarung gilt CART 1.0 mit 5.000 Cent.