# internal_home_dashboard
Ein minimalistisches, performantes Dashboard, das als **zentraler Einstiegspunkt** (Landing Page) für das Home Lab dient. Es läuft statisch auf der Synology Web Station und benötigt keine Docker-Container oder externe Abhängigkeiten.

## 🌟 Features

* **Zero Dependencies:** Reines HTML/CSS/JS. Kein Build-Prozess, extrem schnell.
* **Design:** "Ultimate Dark Mode" mit orangenen Akzenten (passend zum Wiki).
* **Responsive:** Funktioniert auf Desktop und Mobile (Grid-Layout).

## 📂 Projektstruktur

```text
/
├── index.html      # Der komplette Code (Single File)
└── README.md       # Diese Datei
```

## 🚀 Installation & Deployment

### Option A: Als Hauptseite (Empfohlen)
Damit das Dashboard erscheint, wenn man nur die IP oder `syn.abbe.de` aufruft:

1.  Verbinde dich per SMB oder File Station mit dem NAS.
2.  Kopiere die `index.html` direkt in den Hauptordner **`/web`**.
3.  Stelle sicher, dass in der **Web Station** der "Default Server" (Standardserver) auf den Ordner `/web` zeigt.

### Option B: In einem Unterordner
1.  Erstelle einen Ordner `/web/dashboard`.
2.  Kopiere die Dateien hinein.
3.  Erstelle in der Web Station ein "Benutzerdefiniertes Portal" oder ändere den Pfad des Default Servers.

## 🛠️ Konfiguration & Anpassung

### Neue Kacheln (Links) hinzufügen
Suche in der `index.html` nach dem Bereich `<div class="grid">`. Kopiere einen bestehenden `<a class="card">...</a>` Block und passe ihn an:

```html
<a href="[https://dein-dienst.syn.abbe.de](https://dein-dienst.syn.abbe.de)" class="card" target="_blank">
    <div class="icon">🚀</div>
    <div class="info">
        <h2>Name des Dienstes</h2>
        <p>Kurze Beschreibung</p>
    </div>
</a>
```

### Farben ändern (CSS)
Das Design wird über CSS-Variablen im `<style>` Block gesteuert:

```css
:root {
    --bg-color: #121212;      /* Hintergrund */
    --card-bg: #1e1e1e;       /* Farbe der Kacheln */
    --accent: #ff9100;        /* Akzentfarbe (Orange) */
    /* ... */
}
```
