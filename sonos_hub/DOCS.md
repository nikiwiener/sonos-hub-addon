# Sonos-Hub (Add-on)

Hub für Mini-Panel, Web-Panel und iOS-App **ohne Sonos**: In der Betriebsart `ma` übersetzt er die Geräte von
Music Assistant (Sendspin) in das Hub-Protokoll. Plan: `docs/PLAN-sendspin.md`, Teil A und §15.

- Erreichbar unter `http://<HA-IP>:8190` (Panel: `/panel/`, Verwaltung: `/admin`). Port 8095 gehört Music Assistant.
- Panel und App brauchen die Adresse **mit Port** (`192.168.x.y:8190`).
- `backends` darf nie `sonos` enthalten. Das Add-on startet außerdem erst, wenn der Hub-Code die Betriebsarten
  kennt (Phase 1).
- Testhub zu Hause: `mqtt_prefix: sonos-hub-test` und `advertise: false`, damit er dem Haupt-Hub nicht in die
  Quere kommt.
- Daten liegen im Add-on unter `/data/hub` und sind Teil der HA-Sicherung.
