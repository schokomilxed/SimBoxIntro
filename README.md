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

## Varianten

Zwei eigenständige Dateien, jede für sich vollständig:

- **Schwarz** – `simbox-intro-schwarz.html`: dunkler Grund, jedes Level mit eigener Akzentfarbe von warm (Mensch) bis kühl (System).
- **Schwarz in DIN Pro** – `simbox-intro-schwarz-din.html`: wie Schwarz, aber in DIN Pro. Die Schrift ist
  lizenzpflichtig und nicht im Repo: Die Seite nimmt die auf dem Abspielrechner installierte DIN Pro oder
  die Dateien aus einem Ordner `fonts/` neben der HTML-Datei (`DINPro-Light`, `-Regular`, `-Medium`,
  `-Bold`, `-Black` als .woff2/.woff/.otf/.ttf). Fehlt beides, erscheint ersatzweise Barlow.
  Zeilen, die in DIN Pro zu breit werden, setzt die Seite automatisch kleiner.
- **Lila** – `simbox-intro-lila.html`: der dynamisch wabernde Verlauf der übrigen Medienflächen als Hintergrund,
  weiße Schrift, Akzente in Dunkelviolett. Ein weißer Lichtfleck wandert pro Level die Wand entlang.
  Die Farben stehen im CSS unter `#stage.lila` und `#wave`.

## Schrift

Barlow Condensed / Barlow kommen von Google Fonts. Ohne Internet greift eine Systemschrift –
für den Offline-Betrieb die Schrift lokal ablegen oder `--display` / `--text` im CSS auf die
CI-Schrift setzen.

## Inhalte anpassen

Titel, Schlagworte, Erklärungen und Beispiele stehen oben im Skript im Array `LEVELS`.
