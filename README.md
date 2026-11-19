# 🏰 Einhorn-Familie – Das Schloss-Abenteuer

HTML5-Spiel (eine einzige `index.html`, kein Build-Schritt) mit einer Einhorn-Familie, einer Prinzessin, einem Schloss und Spielständen in Firebase.

**Spielen:** https://thomasschlerethbm.github.io/Einhorn-Familie/ (nachdem GitHub Pages aktiviert ist)

## Steuerung

| Taste | Aktion |
|---|---|
| ← → ↑ ↓ | Fliegen / Laufen / Treppe |
| 1–6 | Einhorn wählen (Papa, Mama, Oma, Opa, Kind, Bruder) |
| Leertaste | Regenbogen |
| K | Kacka 💩 |
| T | Traktor an/aus 🚜 |
| G | Prinzessin an/aus 👸 |
| R | Auf ein Einhorn steigen / absteigen (Sattel nötig) |
| F | Einhorn mit Karotte füttern |
| H | Ins Schloss gehen / Schloss verlassen |
| Enter | Kiosk, Kleiderschrank, Thron |
| W | Winken (auf dem Balkon winken die Einhörner zurück) |
| P | Pause, Spielstand speichern und laden |

## Spielstände & Bestenliste (Firebase)

Das Spiel nutzt die Firebase Realtime Database des Projekts `deutsch-pokemon-regeln` unter dem Pfad `einhornfamilie/`:

- `einhornfamilie/spielstaende/<name>` – gespeicherte Spielstände
- `einhornfamilie/bestenliste` – Highscores

In der Firebase-Konsole → Realtime Database → **Regeln** muss dieser Eintrag ergänzt werden (neben dem bestehenden `wortmonster`-Eintrag):

```json
"einhornfamilie": { ".read": true, ".write": true }
```

Ohne Verbindung speichert das Spiel automatisch nur lokal im Browser. Für ein eigenes Firebase-Projekt einfach `FIREBASE_CONFIG` und `DB_URLS` oben in der `index.html` ersetzen.
