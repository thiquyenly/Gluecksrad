# Glücksrad mit Abstimmungsfaktor

Eine Web-App im Spielhallen-/Showbühnen-Look. Man gibt eine Frage und mehrere
Antworten ein, das Rad dreht sich 5 Sekunden mit Spannungston und kürt eine
Gewinner-Antwort mit Fanfare.

## Starten
Die Datei `index.html` einfach im Browser öffnen (Doppelklick). Es wird kein
Server und keine Installation benötigt.

## Dateien
- `index.html` – Gerüst der Seite (welche Elemente existieren)
- `style.css`  – Aussehen: Neon-Look, Glow, blinkende Lampen
- `script.js`  – Logik: Rad zeichnen, Gewinner auslosen, drehen, Töne

## Der Abstimmungsfaktor
Jede Antwort hat einen Faktor (Zahl ab 1). Beim Drehen wird nach dem
"Lostopf-Prinzip" ausgelost: Faktor 5 bedeutet 5 Lose, Faktor 1 nur 1 Los.
Antworten mit höherem Faktor gewinnen also wahrscheinlicher.

Über den Schalter "Tortenstücke nach Faktor vergrößern" kann man wählen, ob die
Stücke auf dem Rad zusätzlich proportional zum Faktor dargestellt werden.

## Eigene Musikdateien (optional)
Standardmäßig werden Spannungston und Fanfare im Browser erzeugt (Web Audio
API). Für den Applaus am Ende kannst du eine echte MP3 hinterlegen: Lege eine
Datei `applause.mp3` in den Ordner `sounds/`. Die App spielt sie dann beim
Gewinner ab. Fehlt die Datei, erzeugt die App einen Ersatz-Applaus selbst.

Hinweis: Manche Browser blockieren lokale MP3s bei reinem Doppelklick auf
index.html. Falls der Applaus nicht kommt, im Ordner einen kleinen Server
starten mit `python -m http.server` und dann http://localhost:8000 öffnen.

## Mögliche Erweiterung (Backend)
Statt der lokalen Faktoren könnte ein Server (Python/PHP/Go ...) echte
Abstimmungsstimmen sammeln und als Faktoren zurückliefern. Das Frontend würde
diese per HTTP-Request (fetch) laden. Die Architektur bleibt dabei gleich.
