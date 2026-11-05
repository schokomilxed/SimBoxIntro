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
- **Lila** – `simbox-intro-lila.html`: der dynamisch wabernde Verlauf der übrigen Medienflächen als Hintergrund,
  weiße Schrift, Akzente in Dunkelviolett. Ein weißer Lichtfleck wandert pro Level die Wand entlang.
  Die Farben stehen im CSS unter `#stage.lila` und `#wave`.

## Rahmenausgleich

Die Inhalte liegen auf einer virtuellen Fläche, in der die Monitorrahmen mitgezählt werden. Was hinter
einem Rahmen liegt, wird nicht gezeigt: Schrift und Linien laufen „hinter dem Rahmen“ durch, statt am
Stoß zu springen. Auf einem normalen Bildschirm ohne Rahmen sieht man deshalb an den Stößen einen
kleinen Versatz – das ist gewollt.

Monitore: LG UltraGear 34G600A-B (34", 21:9, 3440 × 1440, gebogen). Pixelabstand 0,23175 mm →
aktive Fläche 797,2 × 333,7 mm, Außenmaß ohne Fuß 809 × 358,9 mm. Jeder Monitor bekommt
1720 × 720 px, 1 px der Bühne entspricht also 0,4635 mm. Die obere Reihe ist um 180° gedreht
montiert, an der Mittelfuge treffen die beiden schmalen Oberkanten aufeinander.

LG nennt die einzelnen Rahmenbreiten nicht. Voreingestellt sind je 9 mm Rand (seitlich und oben) plus
2 mm Luft zwischen den Monitoren, also 20 mm ≈ 43 px je Stoß, waagerecht und senkrecht.

**Vor Ort einmessen:** Taste **K** zeigt ein Testbild aus schrägen Linien und Kreisen.
- ←/→ ändert den Ausgleich zwischen den Spalten, ↑/↓ zwischen den Reihen (mit Shift in 10er-Schritten).
- Richtig ist es, wenn die Linien und Kreise hinter den Rahmen gerade weiterlaufen.
- 0 setzt auf die Datenblattwerte zurück, K beendet das Einmessen.

Der Browser merkt sich die Werte. Damit sie fest in der Datei stehen, die angezeigten mm-Werte im
Skript unter `FRAME` eintragen (`sideMm`/`gapXmm` für die Spalten, `topMm`/`gapYmm` für die Reihen).

## Schrift

Barlow Condensed / Barlow kommen von Google Fonts. Ohne Internet greift eine Systemschrift –
für den Offline-Betrieb die Schrift lokal ablegen oder `--display` / `--text` im CSS auf die
CI-Schrift setzen.

## Inhalte anpassen

Titel, Schlagworte, Erklärungen und Beispiele stehen oben im Skript im Array `LEVELS`.
