SPEC [kurzer Name / ID] · Version [0.1] · Status: Entwurf

SO STARTET DER PRODUCT OWNER
Ersetze die eckigen Klammern durch kurze Sätze. Stichpunkte genügen. Was du noch nicht weißt, bleibt als „offen“ mit einer zuständigen Person stehen. Technik und Messung ergänzt ihr gemeinsam. Beispieltexte sind Hilfen, keine Vorgaben.

1. Für wen lösen wir welches Problem?
Der Auftrag kommt von [Team / Vorstand / Geschäftsführung / strategische Initiative / andere Stelle].
Er trägt zu [übergeordnetes Ziel und Link zum Auftrag] bei. Vorgegeben sind [Ziel, Termin, Budget oder Pflichtumfang].
PO und Team dürfen selbst über [Spielraum] entscheiden. Änderungen außerhalb davon bestätigt [zuständige Person / Gremium].
Als [Zielgruppe] möchte ich [Aufgabe erledigen], damit [Nutzen].
Heute passiert dabei [beobachtbares Problem]. Das wissen wir aus [Feedback, Beobachtung oder Daten; sonst: noch zu prüfen].
Beispiel: Kunden möchten ihre Auswahl korrigieren, damit sie die richtige Menge bestellen. Heute ist die Mengenänderung umständlich.

2. Was soll besser werden?
Wenn wir [kleine Änderung] ermöglichen, erwarten wir [beobachtbare Verbesserung], weil [Annahme].
Wir erkennen einen Nutzen daran, dass [Signal oder Kennzahl] sich von [Ausgangswert / noch offen] auf [Ziel / gemeinsam festzulegen] verändert.
Dabei darf [unerwünschte Nebenwirkung] nicht zunehmen.
Beispiel: Mehr Kunden erreichen den Checkout; Preisfehler dürfen nicht zunehmen. Messdetails klären wir mit dem Messpartner.

3. Was ist der kleinste sinnvolle Umfang?
In dieser Änderung ermöglichen wir [höchstens wenige konkrete Fähigkeiten].
Bewusst später behandeln wir [Wünsche außerhalb des Umfangs].
Slice: Ist die Spec mit abgegrenztem Kontext verständlich, ohne große Systemerklärung umsetzbar und eigenständig überprüfbar?
Wenn nein: [kleinere Specs mit eigenen Prüffällen und benötigtem Kontext]; den Schnitt bestätigen PO und Team.
Wir investieren höchstens [Teamaufwand] und [KI-Budget]; bei [Prüfpunkt] entscheiden wir über Fortsetzung oder kleineren Umfang.
Den Rahmen vereinbare ich mit [Team / zuständige Person].

4. Zeige das gewünschte Verhalten an Beispielen.
AK-01: Gegeben [Ausgangslage], wenn [Aktion], dann [sichtbares, prüfbares Ergebnis].
AK-02: Gegeben [Grenzfall], wenn [Aktion], dann [erwartete Reaktion].
AK-03: Gegeben [Fehlerfall], wenn [ungültige Aktion], dann [Rückmeldung und was unverändert bleibt].
Nach [weiterer Aktion] muss [neuer Zustand] sichtbar sein.
Beispiel: Gegeben ein Artikel mit Menge 1, wenn ich ihn erneut hinzufüge, dann sehe ich eine Position mit Menge 2.
Prüffragen: Was passiert bei leer, 0, zu viel, ohne Berechtigung oder nach wiederholtem Klicken? Nur passende Fälle aufnehmen; AK-IDs später nicht neu durchnummerieren.

5. Was müssen wir noch entscheiden?
Offene Frage: [Frage]. Klärt [Name] bis [Termin]. Blockiert [betroffene Umsetzung / nichts].
Fachlich bestätigt durch: [PO / Fachpartner, Datum]; bis dahin bleibt diese Spec ein Entwurf.

GEMEINSAM MIT DEM TEAM ERGÄNZEN
6. Technische Vereinbarung – Team führt, PO klärt fachliche Folgen.
Betroffene Schnittstelle / Eingaben: [Vertrag oder Link].
Ergebnisse, Fehler, Berechtigungen und Datenschutz: [Regeln / offene Entscheidungen].
Tests: [AK-IDs, Gegenfälle, Integrations- und Regressionstests].
Fachliche Abnahme: [Person, Szenarien, Testversion und Termin / Auslöser].
Release, Betriebskontrolle und Rücknahme: [Plan, Owner und Auslöser].
Bei kleinen Aufgaben genügt ein Verweis auf bereits geltende Standards.

Reliability & Observability · OPTIONAL
Nur soweit relevant ausfüllen. Für unkritische Änderungen reicht eine sehr kleine oder keine Angabe; ein Verweis auf geltende Standards kann genügen.
Die Tiefe richtet sich nach Kritikalität, möglichem Schaden, Nutzungshäufigkeit, Abhängigkeiten und Wiederherstellbarkeit.
Kritikalität: [hoch / mittel / niedrig]
Monitoring: [Welche Metriken, Logs oder Traces werden benötigt?]
Alert wenn: [Welche konkrete Abweichung soll einen Alert auslösen? Reaktion, Zuständigkeit und Eskalation klären.]
SLO / erwartete Verfügbarkeit: [optional, nur wenn für die Komponente relevant]
Verhalten bei Ausfall: [Retry, Fallback, Rollback, Degradation, manueller Eingriff oder anderes Verhalten]
Dashboard / Tool: [optional: Link zu Datadog, Grafana, Sentry oder einem anderen System]
Kritikalität, akzeptables Risiko, Alert-Schwellen, SLOs, Eskalation und Freigabe bestätigen die verantwortlichen Menschen.

7. Wirkung prüfen – Messpartner unterstützt.
Primäre Kennzahl / Zähler / Nenner: [Definition].
Quelle / Ereignisse / Vergleich / Zeitraum: [Plan].
Schutzkennzahlen und Entscheidungsregel: [Grenzen, noch offene Daten].
Scorecard: [Link]. Über Fortsetzung entscheidet [Person] bei [Prüfpunkt].

8. Einen verlässlichen Stand festhalten.
Owner: [Name]. Führende Quelle: [Link].
Bestätigte Version und unveränderlicher Stand: [Version + Commit-Link / Dokumentrevision].
KI-Aufträge, Tests, Review und Abnahme beziehen sich auf [diesen Stand].
Release verbindet [Spec-Stand, geprüfte Code-Version und Nachweise].
Änderungsverlauf: [Version, Datum, Änderung, Grund, betroffene AK-IDs, Bestätigung].
Bei Änderungen laufende KI-Aufträge auf Auswirkungen prüfen und den vereinbarten Stand ausdrücklich festhalten.

KURZER CHECK VOR DER UMSETZUNG
Kann eine andere Person an meinen Beispielen erkennen, was richtig wäre?
Sind Umfang, Verantwortung und Investitionsrahmen klar?
Sind kritische offene Fragen geklärt und die Regeln menschlich bestätigt?
Verwenden alle denselben Spec-Stand?