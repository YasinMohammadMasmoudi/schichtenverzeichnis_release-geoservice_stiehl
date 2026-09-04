# Schichtenverzeichnis — Releases (Geoservice Stiehl)

Öffentlicher Auslieferungskanal für die App **Schichtenverzeichnis** von Geoservice Stiehl.
Der Quellcode liegt privat in [`schichtenverzeichnis-geoservice_stiehl`](https://github.com/YasinMohammadMasmoudi/schichtenverzeichnis-geoservice_stiehl).

## Wozu dieses Repository

Die App prüft bei jedem Start `version.json` auf dem `main`-Branch
(`lib/update_gate.dart`). Ist `build` dort höher als der eigene Build, wird
das unter `apk` verlinkte Paket per `ota_update` installiert.

**Dieses Repository muss öffentlich bleiben.** Die App liest
`raw.githubusercontent.com` ohne Anmeldung; privat liefert GitHub 404 und die
Aktualisierung schlägt still fehl — die App läuft dann für immer auf der
alten Version weiter.

## Neue Version veröffentlichen

1. Im Quell-Repository `version:` in `pubspec.yaml` erhöhen und
   `flutter build apk --release` bauen.
2. Hier ein Release `vX.Y.Z` anlegen und `schichtenverzeichnis.apk` als Asset anhängen.
3. `version.json` anpassen: `build` (muss steigen), `version`, `apk` (URL
   des neuen Assets) und `notes` (wird dem Nutzer im Update-Dialog angezeigt).

`build` ist der Zähler hinter dem `+` in `pubspec.yaml` und entscheidet
allein, ob aktualisiert wird — `version` ist nur Anzeigetext.

## Inhalt

APKs werden **nicht** eingecheckt, sondern hängen als Release-Assets. Im
Repository liegen nur `version.json` und diese Datei.
