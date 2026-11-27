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
- Spotify: Suche und Stöbern laufen standardmäßig über eine eigene Spotify-App des Hubs (Option
  `spotify_client_id`, Anmeldung in der Verwaltung unter „Spotify“; dort steht auch die Redirect-URI für das
  Spotify-Dashboard). Spotify erlaubt `http://` nur für `127.0.0.1`: Ohne weiteres Zutun ist das
  `http://127.0.0.1:8190/spotify/callback`, und die Adresse, die danach nicht lädt, kommt per Kopieren in die
  Verwaltung. Ist der Hub per HTTPS erreichbar, `spotify_redirect_uri` auf `https://…/spotify/callback` setzen –
  dann landet die Anmeldung direkt beim Hub. Abgespielt wird über den Spotify-Anbieter von Music Assistant. Umschalten auf Suche über
  Music Assistant: Verwaltung → „Music Assistant“ → „Spotify suchen und stöbern“.
