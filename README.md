# 3D Gaussian Splatting Galerie

Mit dem iPhone und [Scaniverse](https://scaniverse.com) aufgenommene Szenen, präsentiert im Browser via [gsplat.js](https://github.com/huggingface/gsplat.js).

## Live-Demo

→ https://DEIN-NAME.github.io/js-3dgs

## Struktur

```
index.html      Galerie-Übersicht
viewer.html     3D-Viewer (Orbit-Navigation)
scans.json      Scan-Liste
scans/          .ply-Dateien und optionale Vorschaubilder
```

## Neuen Scan hinzufügen

1. `.ply`-Datei aus Scaniverse exportieren und in `scans/` ablegen
2. Optional: Screenshot als `.jpg` daneben legen
3. Eintrag in `scans.json` ergänzen:

```json
{
  "name": "Mein Scan",
  "description": "Kurze Beschreibung",
  "file": "scans/mein-scan.ply",
  "thumbnail": "scans/mein-scan.jpg"
}
```

4. Committen und pushen – fertig.

## Scaniverse-Export

App → Scan auswählen → **Teilen** → **Gaussian Splat (.ply)** → per AirDrop auf den Mac.

Für kleinere Dateigrößen kann die `.ply` mit [SuperSplat](https://playcanvas.com/supersplat) in `.spz` konvertiert werden (bis zu 10× kleiner).

## Lokaler Test

Da `scans.json` per `fetch()` geladen wird, ist ein lokaler Webserver nötig:

```bash
npx serve .
# oder
python3 -m http.server 8080
```

Dann im Browser: `http://localhost:8080`

## GitHub Pages einrichten

```bash
git remote add origin https://github.com/DEIN-NAME/js-3dgs.git
git push -u origin main
```

GitHub → Settings → Pages → Branch: **main** / root → Save.
