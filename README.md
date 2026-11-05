# Sim.Box Intro – Level des automatisierten Fahrens

Idle-Animation für die Sim.Box-Station: zwei 4×2-Bildschirmwände, je 6880 × 1440 px
(ein Bildschirm 1720 × 720 px).

`index.html` zeigt nacheinander einen Einstieg und die Level 0–5 nach SAE J3016, jeweils deutsch
und englisch, als typografische Animation in drei Takten: Titel mit großer Ziffer → Schlagwort über
die volle Breite → Bedeutung, „Wer fährt?“, Beispiele und Füße/Hände/Augen/Kopf. Fließtext bleibt
immer innerhalb eines Bildschirms, nur die große Display-Schrift läuft über die Stöße.
Ein Durchlauf dauert gut 2,5 Minuten und wiederholt sich dann.

## Abspielen

`index.html` im Browser im Vollbild auf 6880 × 1440 öffnen. Bei anderer Fenstergröße skaliert die
Bühne mit. Es braucht keinen Server und keine weiteren Dateien.

| Parameter    | Wirkung                                                        |
| ------------ | -------------------------------------------------------------- |
| `?grid=1`    | Bildschirmstöße einblenden (auch Taste G)                      |
| `?level=3`   | mit diesem Level starten                                       |
| `?offset=8`  | Start um n Sekunden verzögern, z. B. für die zweite Seite      |
| `?speed=1.5` | schneller / langsamer abspielen                                |

## Schrift

Barlow Condensed / Barlow kommen von Google Fonts. Ohne Internet greift eine Systemschrift –
für den Offline-Betrieb die Schrift lokal ablegen oder `--display` / `--text` im CSS auf die
CI-Schrift setzen.

## Inhalte anpassen

Titel, Schlagworte, Erklärungen und Beispiele stehen oben im Skript im Array `LEVELS`.
