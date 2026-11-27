# Sonos-Hub Add-ons

Home-Assistant-Add-on-Repository für den Sonos-Hub. Hier liegen nur die Add-on-Beschreibungen;
die Images werden im (privaten) Haupt-Repository gebaut und liegen privat auf GHCR.
Inhalte werden von `scripts/addon-release.sh` im Haupt-Repository geschrieben – nicht von Hand ändern.

## Einrichten in Home Assistant

1. Einstellungen → Add-ons → Add-on-Store → ⋮ → **Repositories**:
   `https://github.com/nikiwiener/sonos-hub-addon`
2. Add-on-Store → ⋮ → **Registries** → hinzufügen: Registry `ghcr.io`, Benutzer `nikiwiener`,
   Passwort = GitHub-Token (classic) nur mit `read:packages`.
3. „Sonos-Hub“ installieren, Konfiguration prüfen, starten.
