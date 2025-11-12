
# 🎹 NUMERIC

This project renders an **interactive piano keyboard** based on a given MusicXML file.  
It highlights all the notes used in the sequence with **red (or customizable) circles** (stickers), numbered in order of appearance.  
Hovering over a key displays its **German note name**.

Perfect for use in educational contexts — and can easily be **embedded** into other websites (e.g., via GitHub Pages).

---

## 🚀 Features

- **MusicXML Parsing** — reads any valid `.musicxml` file  
- **Dynamic Keyboard Range** — adjusts automatically to show lowest & highest notes  
- **Visual Note Markers** — red circles with sequence numbers  
- **Hover Labels** — German note names (`C`, `Cis`, `Des`, etc.)  
- **Customizable Colors** — via URL parameters  
- **Embeddable Widget** — runs directly in an `<iframe>`  

---

## 🧩 Usage

1. Host this repository on **GitHub Pages**  
   (e.g. at `https://yourname.github.io/yourrepo/`)

2. Place your MusicXML files under `/scores/`, for example:
```

yourrepo/
├─ piano.html
└─ scores/
└─ alors-a-C.musicxml

````

3. Use the following embed code anywhere on the web:

```html
<iframe
  src="https://yourname.github.io/yourrepo/piano.html?musicxml=scores/alors-a-C.musicxml&color=red"
  width="100%"
  height="320"
  style="border:0;"
  loading="lazy">
</iframe>
````

---

## ⚙️ URL Parameters

| Parameter  | Description                                                    | Example                     |
| ---------- | -------------------------------------------------------------- | --------------------------- |
| `musicxml` | Path or URL to the MusicXML file                               | `scores/alors-a-C.musicxml` |
| `color`    | Marker color (CSS value or hex code)                           | `red` or `%23FF0000`        |
| `bg`       | Background color of keyboard area (optional)                   | `#f9f9f9`                   |
| `label`    | Show/hide note labels (`true`/`false`)                         | `true`                      |
| `font`     | Font family for sequence numbers                               | `Arial`                     |
| `scale`    | Visual scale factor for keyboard size (e.g. `1.0`, `1.5`, `2`) | `1.2`                       |

Example with multiple parameters:

```html
<iframe
  src="https://yourname.github.io/yourrepo/piano.html?musicxml=scores/alors-a-C.musicxml&color=%23e22&bg=%23fafafa&scale=1.2"
  width="100%"
  height="360"
  style="border:0;"
  loading="lazy">
</iframe>
```

---

## 🧠 How It Works

* The script fetches and parses the MusicXML file.
* It extracts all note pitches and determines the required range.
* An SVG piano keyboard is rendered dynamically.
* Each pitch used in the sequence gets a numbered red marker.
* Hovering on a key shows the note name in German notation.

---

## 💡 Credits

Developed by **Adrián Artacho**
Website: [www.artacho.at](https://www.artacho.at)
© 2025 – freely reusable for educational and artistic projects.

---

## 🧱 License

MIT License.
You are free to use, modify, and embed this visualizer in your own projects.

---

## To-Do (branch out for development)

* BIG ISSUE: wrong piano keys.
* Do not process hidden (invisible) notes. This way, i don't need to delete them in the maxmsp file.
* When the same key is used several times in the sequence, have a different circle for each.
* 'simplified' tag should, out of the box, remove consecutive repetitions of the same key
* it would be nice for the key to light up on hoovering (and large note name)
