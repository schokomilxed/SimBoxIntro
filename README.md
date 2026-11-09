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
- **Lila Bold** – `simbox-intro-lila-bold.html`: Animation, Größen und Takte wie Lila DIN, die CI dient als
  Inspiration: weißes Raster im Hintergrund, Klammerecken, die über die Wand wandern und auf Rasterlinien
  einrasten (Ziffer → ganze Wand → Ziffer), ein helles Rasterband als Übergang zwischen den Takten,
  deutsche Titel Bold, englische Titel Regular, alles in Weiß, keine Konturschrift.
- **Lila CI** – `simbox-intro-lila-ci.html`: Versuch im Gestaltungssystem der übrigen Medienflächen.
  Weißes Raster (Zellen auf allen Bildschirmen gleich), Flächen mit weißen Eckwinkeln, deutsche Titel
  DIN Pro Bold, englische Titel DIN Pro Regular, alle Texte weiß, keine Konturschrift. Einheitliche
  Übergänge: Flächen bauen sich Rasterspalte für Rasterspalte auf, Texte blenden weich ein. Links ein
  Bildschirm mit Stationstitel, Levelziffer und Fortschritt; „frei“ bei Füße/Hände/Augen/Kopf als Fläche
  mit weißem Rand. Tasten H, G, ←/→, Leertaste, F (kein Sicherheitsrand, das Layout folgt dem Raster).
- **Lila** – `simbox-intro-lila.html`: der dynamisch wabernde Verlauf der übrigen Medienflächen als Hintergrund,
  weiße Schrift, Akzente in Dunkelviolett. Ein weißer Lichtfleck wandert pro Level die Wand entlang.
  Die Farben stehen im CSS unter `#stage.lila` und `#wave`.

## Eigenständige Dateien zum Verschicken

`standalone/simbox-intro-lila-ci-standalone.html` und `standalone/simbox-intro-lila-bold-standalone.html`
enthalten DIN Pro eingebettet (je ca. 0,9 MB) und brauchen weder den Ordner `fonts/` noch Internet.
Die Weitergabe der Schrift muss die DIN-Pro-Lizenz abdecken. Nach Änderungen an den Hauptdateien
die Standalone-Dateien neu erzeugen.

## Schrift

Barlow Condensed / Barlow kommen von Google Fonts. Ohne Internet greift eine Systemschrift –
für den Offline-Betrieb die Schrift lokal ablegen oder `--display` / `--text` im CSS auf die
CI-Schrift setzen.

## Inhalte anpassen

Titel, Schlagworte, Erklärungen und Beispiele stehen oben im Skript im Array `LEVELS`.

## Filme

Gerendert aus den DIN-Pro-Varianten: H.264, 6880 × 1440, 30 fps, 2:34,6 min, nahtlos loopbar,
Sicherheitsrand 110 px.

- `SimBoxIntro_schwarz-din_6880x1440_30fps.mp4` – im Repo.
- `SimBoxIntro_lila-din_6880x1440_30fps.mp4` – mit 136 MB zu groß für GitHub (Grenze 100 MB pro Datei),
  liegt deshalb nur lokal und steht in der `.gitignore`.
