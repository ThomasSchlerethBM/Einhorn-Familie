# 🏰 Einhorn-Familie – Das Schloss-Abenteuer

HTML5-Spiel (eine einzige `index.html`, kein Build-Schritt) mit einer Einhorn-Familie, einer Prinzessin, einem Schloss und Spielständen in Firebase.

**Spielen:** https://thomasschlerethbm.github.io/Einhorn-Familie/ (nachdem GitHub Pages aktiviert ist)

## Steuerung

| Taste | Aktion |
|---|---|
| ← → ↑ ↓ | Fliegen / Laufen / Treppe |
| 1–9 | Einhorn wählen (Papa, Mama, Oma, Opa, Kind, Bruder, eigene Babys) |
| Leertaste | Regenbogen (Einhorn) / Springen (Prinzessin) |
| K | Kacka 💩 |
| T | Traktor an/aus 🚜 |
| G | Prinzessin an/aus 👸 |
| R | Auf ein Einhorn steigen / absteigen (Sattel nötig) |
| F | Einhorn mit Karotte füttern |
| H | Ins Schloss gehen / Schloss verlassen |
| Enter | Kiosk, Kleiderschrank, Thron |
| W | Winken (auf dem Balkon winken die Einhörner zurück) |
| P | Pause, Spielstand speichern und laden |
| M | Musik an/aus |
| X | Prinz spielt mit (2. Spieler) |
| L | Kuscheltier ablegen / aufheben |

### Zu zweit spielen (Prinz)

Mit **X** kommt der Prinz überall dazu (draußen, im Schloss, auf dem Balkon, im Pokalzimmer, im Tanzsaal). Spieler 2 läuft mit **A D**, springt mit **W**, geht Treppen mit **W/S** und nutzt **Q** an Türen. In ein anderes Zimmer geht es nur, wenn **beide zustimmen**: Einer schlägt es an der Tür vor, der andere bestätigt (👸 Enter / 🤴 Q). Beim Reiten sitzen beide auf demselben Einhorn, der Prinz zaubert mit Q einen Regenbogen.

### Kleiderschrank

12 Kleider, 6 Schlafanzüge, 8 Kopfbedeckungen und 20 Kuscheltiere für die Prinzessin. Der Prinz hat oben auf der Galerie seinen eigenen Schrank: 3 Uniformen, 6 Roben, 6 Ritterrüstungen und 6 Schlafanzüge mit Schlafmütze (Prinz: Q, Prinzessin: Enter). Ein Kuscheltier trägt die Prinzessin überall mit (auch beim Reiten und Tanzen) und kann es mit **L** irgendwo ablegen und später wieder aufheben.

### Tanzsaal (1 oder 2 Spieler)

| | 👸 Prinzessin (Spieler 1) | 🤴 Prinz (Spieler 2) |
|---|---|---|
| Laufen | ← → | A D |
| Figur | Leertaste | Q |
| Pirouette | Figur allein | Figur allein |
| Sprung | ↑ + Figur | W + Q |
| Knicks / Verbeugung | ↓ + Figur | S + Q |
| Gleiten | ← → + Figur | A D + Q |

Stehen beide nah beieinander und drücken fast gleichzeitig, gibt es eine gemeinsame Figur: Walzer, Hebefigur (↑), Dip (↓) oder Doppel-Pirouette (← →). Im Takt des Herzens gedrückt = Perfekt (×2), abwechslungsreiche Figuren erhöhen die Combo.

Für Tanzpunkte gibt es 50 Pokale (Bronze, Silber, Gold, Kristall, Regenbogen) mit Verleihung vor Publikum und Blumen. Die Pokale stehen im Pokalzimmer.

### Einhorn-Zucht

Babys (Kind, Bruder) werden nach 20 Karotten groß. Große Einhörner bekommen nach 10 Karotten ein Baby. Eigene Babys kann man am Kiosk verkaufen (Baby 25⭐, groß 60⭐). Maximal 12 Einhörner auf der Weide.

## Spielstände & Bestenliste (Firebase)

Das Spiel nutzt die Firebase Realtime Database des Projekts `deutsch-pokemon-regeln` unter dem Pfad `einhornfamilie/`:

- `einhornfamilie/spielstaende/<name>` – gespeicherte Spielstände
- `einhornfamilie/bestenliste` – Highscores

In der Firebase-Konsole → Realtime Database → **Regeln** muss dieser Eintrag ergänzt werden (neben dem bestehenden `wortmonster`-Eintrag):

```json
"einhornfamilie": { ".read": true, ".write": true }
```

Ohne Verbindung speichert das Spiel automatisch nur lokal im Browser. Für ein eigenes Firebase-Projekt einfach `FIREBASE_CONFIG` und `DB_URLS` oben in der `index.html` ersetzen.
