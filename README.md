# ikira-web

Webseite der App IKIRA unter `ikira.byklug.de`: Vorstellung, Impressum, Datenschutzerklärung und „Konto löschen“ (für Google Play). Kein Teil der App selbst; die App liegt in einem eigenen Repository.

## Aufbau

Schlichtes HTML und CSS in `public/`, ohne Build-Schritt und ohne externe Dateien (keine Webfonts, kein JavaScript, keine Cookies).

| Datei | Adresse |
| --- | --- |
| `public/index.html` | `/` |
| `public/impressum.html` | `/impressum` |
| `public/datenschutz.html` | `/datenschutz` |
| `public/konto-loeschen.html` | `/konto-loeschen` |
| `public/_headers` | Sicherheits-Header für Cloudflare |

Cloudflare liefert `impressum.html` unter `/impressum` aus.

## Veröffentlichen

Cloudflare Pages baut bei jedem Push auf `main` neu.

- Projekt: mit dem GitHub-Repository `ikira-official/ikira-web` verbunden
- Build-Befehl: leer
- Ausgabeordner: `public`
- Eigene Domain: `ikira.byklug.de`, bei Hetzner DNS als CNAME auf `<projekt>.pages.dev`

Lokal ansehen: `npx serve public` oder die HTML-Dateien direkt im Browser öffnen.

## Vor dem Livegang

- [ ] Ladungsfähige Anschrift im Impressum und in der Datenschutzerklärung (`[Anschrift folgt]`)
- [ ] Datenschutzerklärung juristisch prüfen lassen
- [ ] Mit `[prüfen]` markierte Angaben gegen die aktuelle Anbieter-Doku prüfen (Anthropic: Training und Aufbewahrung; Resend: Auftragsverarbeitung und Protokolle; Supabase: Backups)
- [ ] Auftragsverarbeitungsverträge abschließen bzw. akzeptieren: Supabase, Anthropic, Resend, Cloudflare
- [ ] Speicherdauer der KI-Protokolle festlegen (App, M11)
- [ ] Abschnitt zu Absturzberichten, sobald das Werkzeug feststeht (App, M10)
- [ ] Menüpfad unter „Konto löschen“ an die Funktion in der App anpassen (App, M11)
