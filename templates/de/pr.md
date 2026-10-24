PR · [Kurztitel]

Zweck & Small Spec: [Warum? Link zur Spec mit gültiger Version]
Änderung & Abgrenzung: [Was ändert sich? Was ausdrücklich nicht?]
Risiko & betroffene Bereiche: [Mögliche Folgen, Schnittstellen, Daten, Berechtigungen]
Evidence: [Durchgeführte Tests/Checks + Ergebnis + Link; Agenten-Review mit Befunden/Stand; nicht ausgeführte Checks benennen]
Bekannte Einschränkungen & offene Punkte: [Befund, Blocker, Owner; oder keine bekannt]
Betrieb & Rollback (falls relevant): [Monitoring, Alerts, Rücknahme und Wiederherstellung; sonst nicht relevant + Grund]
Review & Merge-Freigabe: [Benannte menschliche Person im Delivery Team; geprüfter Commit/Stand, Entscheidung und Datum]

REVIEW-CHECKLISTE
Bedingte Punkte dürfen mit „nicht relevant“ und kurzer Begründung beantwortet werden.
- [ ] Spec & Umfang: Erfüllt die Änderung die Spec und bleibt sie im vereinbarten Umfang?
- [ ] Verständlichkeit & Architektur: Sind Aufbau, Wartbarkeit und Architektur der Änderung tragfähig?
- [ ] Sicherheit & Datenzugriff: Sind Sicherheit, Datenzugriffe und Berechtigungen angemessen abgesichert? [geprüft / nicht relevant + Grund]
- [ ] Tests & Fehlerfälle: Sind Tests und Checks aussagekräftig und relevante Fehlerfälle abgedeckt?
- [ ] Schnittstellen & bestehende Funktionen: Sind Auswirkungen auf Schnittstellen und bestehende Funktionen geprüft? [geprüft / nicht relevant + Grund]
- [ ] Betrieb & Rücknahme: Bei Betriebsrelevanz: Sind Monitoring, Alerting, Rollback und Wiederherstellung geklärt und nachgewiesen? [geprüft / nicht relevant + Grund]
- [ ] Blockierende Befunde behoben und erneut geprüft; relevante Änderungen nach Freigabe erneut vorgelegt.