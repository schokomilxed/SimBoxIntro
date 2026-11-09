# Sim.Box Intro – Level des automatisierten Fahrens

Idle-Animation für die Sim.Box-Station: zwei 4×2-Bildschirmwände, je 6880 × 1440 px
(ein Bildschirm 1720 × 720 px).

Beide Dateien zeigen nacheinander einen Einstieg und die Level 0–5 nach SAE J3016, jeweils deutsch
und englisch, als typografische Animation in drei Takten: Titel mit großer Ziffer → Schlagwort über
die volle Breite → Bedeutung, „Wer fährt?“, Beispiele und Füße/Hände/Augen/Kopf. Fließtext bleibt
immer innerhalb eines Bildschirms, nur die große Display-Schrift läuft über die Stöße.
Ein Durchlauf dauert gut 2,5 Minuten und wiederholt sich dann.

## Abspielen

Die gewünschte Datei im Browser im Vollbild auf 6880 × 1440 öffnen. Bei anderer Fenstergröße skaliert die
Bühne mit. Es braucht keinen Server und keine weiteren Dateien.

| Parameter    | Wirkung                                                        |
| ------------ | -------------------------------------------------------------- |
| `?grid=1`    | Bildschirmstöße einblenden (auch Taste G)                      |
| `?level=3`   | mit diesem Level starten                                       |
| `?offset=8`  | Start um n Sekunden verzögern, z. B. für die zweite Seite      |
| `?speed=1.5` | schneller / langsamer abspielen                                |

## Tasten

H blendet die Übersicht ein.

| Taste       | Wirkung                                                                  |
| ----------- | ------------------------------------------------------------------------ |
| H           | Tastenübersicht ein/aus                                                  |
| G           | Bildschirmraster und Sicherheitsrand (gestrichelt) ein/aus               |
| Q / A       | Sicherheitsrand größer / kleiner, mit Shift in 50er-Schritten            |
| 0           | Sicherheitsrand zurück auf 110 px                                        |
| ← / →       | vorige / nächste Szene                                                   |
| Leertaste   | Pause / weiter                                                           |
| F           | Vollbild ein/aus                                                         |

Der Sicherheitsrand ist der Abstand der Texte zum Bildschirmrand (Standard 110 px). Wird er größer,
schrumpft der Inhalt im selben Verhältnis mit, damit alles auf den Bildschirm passt. Der Browser merkt
sich den eingestellten Wert.

## Varianten

Zwei eigenständige Dateien, jede für sich vollständig:

- **Schwarz** – `simbox-intro-schwarz.html`: dunkler Grund, jedes Level mit eigener Akzentfarbe von warm (Mensch) bis kühl (System).
- **Schwarz in DIN Pro** – `simbox-intro-schwarz-din.html`: wie Schwarz, aber in DIN Pro. Die Schrift ist
  lizenzpflichtig und nicht im Repo: Die Seite nimmt die auf dem Abspielrechner installierte DIN Pro oder
  die Dateien aus einem Ordner `fonts/` neben der HTML-Datei (`DINPro-Light`, `-Regular`, `-Medium`,
  `-Bold`, `-Black` als .woff2/.woff/.otf/.ttf). Fehlt beides, erscheint ersatzweise Barlow.
  Zeilen, die in DIN Pro zu breit werden, setzt die Seite automatisch kleiner.
- **Lila in DIN Pro** – `simbox-intro-lila-din.html`: die Lila-Variante in DIN Pro, Schrift wie oben.
- **Lila** – `simbox-intro-lila.html`: der dynamisch wabernde Verlauf der übrigen Medienflächen als Hintergrund,
  weiße Schrift, Akzente in Dunkelviolett. Ein weißer Lichtfleck wandert pro Level die Wand entlang.
  Die Farben stehen im CSS unter `#stage.lila` und `#wave`.

## Schrift

Barlow Condensed / Barlow kommen von Google Fonts. Ohne Internet greift eine Systemschrift –
für den Offline-Betrieb die Schrift lokal ablegen oder `--display` / `--text` im CSS auf die
CI-Schrift setzen.

## Inhalte anpassen

Titel, Schlagworte, Erklärungen und Beispiele stehen oben im Skript im Array `LEVELS`.

## Filme

Gerendert aus den DIN-Pro-Varianten: H.264, 6880 × 1440, 30 fps, 2:34,6 min, nahtlos loopbar,
Sicherheitsrand 110 px.

- `SimBoxIntro_schwarz-din_6880x1440_30fps.mp4`
- `SimBoxIntro_lila-din_6880x1440_30fps.mp4` – liegt wegen der GitHub-Grenze von 100 MB pro Datei in zwei
  Teilen im Repo (`.part0`, `.part1`, nicht neu komprimiert). Zusammensetzen:

  ```sh
  cat SimBoxIntro_lila-din_6880x1440_30fps.mp4.part* > SimBoxIntro_lila-din_6880x1440_30fps.mp4
  shasum -a 256 -c SHA256SUMS.txt
  ```
