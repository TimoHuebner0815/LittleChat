# LittleChat

**Ein Walkie-Talkie für Kinder, mit dem sie per Stimme Fragen an eine KI stellen: standardmäßig Claude, wahlweise ChatGPT, Gemini, Mistral, Grok oder lokal über Ollama.** Knopf gedrückt halten, fragen, loslassen, Antwort hören. Eltern bestimmen Limits, geben Geräte frei und können die Gespräche nachlesen.

> Inoffiziell, nicht mit Anthropic, OpenAI, Google, Mistral AI, xAI oder Ollama verbunden. „Claude“, „ChatGPT“, „Gemini“ und „Grok“ sind Marken ihrer Anbieter. LittleChat nutzt die öffentlichen APIs mit deinem eigenen API-Schlüssel. Ein Abo (Claude Pro, ChatGPT Plus …) funktioniert nicht.

**Schnellstart:** [littlechat-latest.zip herunterladen](https://github.com/TimoHuebner0815/LittleChat/raw/main/releases/littlechat-latest.zip), entpacken, unter Windows doppelt auf `LittleChat-installieren.cmd` klicken. Alles Weitere erledigt der Installer. Die ganze Anleitung steht [weiter unten](#1-was-du-brauchst).

## Was LittleChat kann

- **Nur Sprache:** Kinder brauchen nicht lesen zu können. Bis 8 Jahre wird jeder Knopf angesagt, Untertitel zeigen den vorgelesenen Satz (pro Kind abschaltbar).
- **Fünf Gesprächsmodi:** Lernen 🎓, Erkunden 🧭, Erforschen 🔍, Kreativ 🖌️ (der Pinsel), Langeweile 🎲, pro Kind freischaltbar.
- **Avatar 🐥:** Mit dem eigenen Knopf erfindet jedes Kind per Stimme bis zu 3 Fantasiefiguren, die die KI im Emoji-Stil malt.
- **Seifenblasen:** Frühere Gespräche schweben als Blasen über den Bildschirm, Antippen setzt sie fort.
- **Eigene Farbe** wählt jedes Kind selbst über die Farbpalette 🎨, ein Farbschloss schützt das Profil vor Geschwistern.
- **Stimmen:** Piper lokal und kostenlos (Standard), wahlweise Google, Microsoft Azure, ElevenLabs oder die Stimme des Geräts, für alle oder pro Kind.
- **Eltern-Bereich** (Zahnrad ⚙ oben rechts 2 Sekunden gedrückt halten): Zeitlimits pro Kind (Uhrzeit, Minuten, Fragen), Gespräche nachlesen und löschen, Geräte freigeben, Name des Assistenten ändern.

## KI-Anbieter

Claude ist der Standard und für Kinder am besten abgestimmt. Im Eltern-Bereich lassen sich weitere Anbieter einrichten, global oder pro Kind: ChatGPT (OpenAI), Gemini (Google), Mistral (Daten in der EU), Grok (xAI) und Ollama (lokal, kostenlos, auf schwacher Hardware langsam). Alle Anbieter außer Claude sind mit der Persona von LittleChat **ungetestet**. Anleitungen pro Anbieter sind im Eltern-Bereich verlinkt.

**Empfehlung (Stand November 2026):** als KI **Claude mit dem Modell Haiku** (Standard, schnell, günstig, für Kinder abgestimmt), als Stimme **Google Cloud Text-to-Speech** mit den Chirp-3-HD-Stimmen (sehr natürlich, 1 Mio. Zeichen im Monat gratis). Piper bleibt die kostenlose Alternative, bei der nichts das Haus verlässt.

## Verantwortung der Eltern

**Eltern tragen die Verantwortung für die Nutzung durch ihre Kinder und haften für sie im Rahmen ihrer Aufsichtspflicht.** Behaltet die Themen und Gespräche im Blick, im Eltern-Bereich lässt sich jedes Gespräch nachlesen. Keine KI ist fehlerfrei. **Nutzung auf eigene Gefahr.**

Dieses Repository enthält nur die **fertigen, signierten Pakete**. Der Quellcode ist nicht öffentlich.

## Installation

**So funktioniert es:** Ein Rechner bei euch zu Hause (der „Server“) läuft die ganze Zeit. Die Kinder benutzen ein Tablet oder Handy. Das Tablet spricht nur mit eurem Server, und nur der Server spricht mit der KI. Dein API-Schlüssel bleibt auf dem Server. Die Installation dauert etwa 30 Minuten. Alles, was LittleChat braucht, lädt der Installer selbst. Dieselbe Anleitung liegt als `INSTALLATION.md` im Paket.

## 1. Was du brauchst

| | |
|---|---|
| **Einen Rechner, der an bleibt** | Windows 10 oder 11, oder Linux (z. B. Raspberry Pi 4/5 mit Raspberry Pi OS **64 Bit**). Ein alter Laptop am Netzteil reicht. Etwa 1 GB freier Platz. |
| **Einen API-Schlüssel** | am besten von Anthropic (Claude). Ein Abo wie Claude Pro oder ChatGPT Plus funktioniert **nicht**. Der Einrichtungs-Assistent zeigt dir, wie du einen Schlüssel mit Ausgabenlimit anlegst. Kosten bei normaler Nutzung: unter 1 $ im Monat. |
| **Ein kostenloses Tailscale-Konto** | Damit das Tablet das Mikrofon benutzen darf, braucht es eine sichere Verbindung (HTTPS). Tailscale erledigt das. Anmelden geht mit Google, Microsoft oder Apple. Der Installer richtet es ein. |
| **Tablets oder Handys** | iPad/iPhone mit Safari oder Android mit Chrome. |

---

## 2. Installieren unter Windows

1. **Herunterladen:** [littlechat-latest.zip](https://github.com/TimoHuebner0815/LittleChat/raw/main/releases/littlechat-latest.zip)
2. **Entpacken:** Rechtsklick auf die ZIP-Datei › „Alle extrahieren…“ › „Extrahieren“. Der Ort ist egal: Der Installer kopiert LittleChat selbst nach `C:\LittleChat`.
3. **Starten:** Im entpackten Ordner doppelt auf **`LittleChat-installieren.cmd`** klicken. Die Datei startet nur das PowerShell-Skript `scripts\install-windows.ps1` mit den nötigen Rechten, so muss niemand PowerShell selbst bedienen.
   - Zeigt Windows „Der Computer wurde durch Windows geschützt“: auf „Weitere Informationen“ und dann „Trotzdem ausführen“ klicken.
   - Fragt Windows „Möchten Sie zulassen, dass…“: auf **Ja** klicken. Der Installer braucht einmal Administratorrechte.
4. **Zuschauen und zwei Fragen beantworten.** Der Installer
   - installiert Node.js (die Laufzeit, in der LittleChat läuft),
   - lädt die kostenlosen deutschen Stimmen (Piper, etwa 200 MB),
   - richtet den Autostart ein: LittleChat startet mit Windows, auch wenn sich niemand anmeldet,
   - schaltet die automatischen Updates ein,
   - fragt **„Tailscale jetzt einrichten?“**: mit Enter bestätigen. Es öffnet sich ein Browserfenster, dort bei Tailscale anmelden. Siehe auch [Abschnitt 4](#4-tailscale-damit-das-tablet-hinkommt).
   - fragt, ob der Rechner am Netzteil **nicht mehr einschlafen** soll: mit Enter bestätigen. Ein schlafender Rechner ist für die Tablets nicht erreichbar. Der Bildschirm geht trotzdem aus.
5. **Am Ende** zeigt das Fenster eine Zusammenfassung und den **Einrichtungscode** (8 Zeichen) und öffnet den Browser. Weiter mit [Abschnitt 5](#5-ersteinrichtung-im-browser).

> Falls etwas schiefgeht: Das Fenster bleibt offen und zeigt den Fehler. Die Installation lässt sich gefahrlos noch einmal starten.

---

## 3. Installieren unter Linux / Raspberry Pi

Im Terminal nacheinander eingeben:

```bash
curl -fsSLO https://github.com/TimoHuebner0815/LittleChat/raw/main/releases/littlechat-latest.zip
mkdir -p ~/littlechat && cd ~/littlechat && unzip -o ../littlechat-latest.zip
sudo bash scripts/install-linux.sh
```

Fehlt `unzip`: `sudo apt install unzip`.

Der Installer lädt Node.js von nodejs.org (Prüfsumme wird geprüft), installiert die Piper-Stimmen, richtet den Dienst `littlechat` mit Autostart und automatischen Updates ein und fragt nach Tailscale. Am Ende stehen eine Zusammenfassung und der **Einrichtungscode** da.

Raspberry Pi mit 32-Bit-System: Das geht noch, Node.js gibt es dafür aber nur noch bis April 2027. Besser gleich Raspberry Pi OS **64 Bit** nehmen.

---

## 4. Tailscale: damit das Tablet hinkommt

**Was ist das?** Tailscale ist wie ein privater, verschlüsselter Tunnel zwischen **deinen eigenen** Geräten. Alle Geräte, die mit deinem Tailscale-Konto angemeldet sind, finden sich gegenseitig, zu Hause und unterwegs. Fremde kommen nicht hinein, und im Internet wird nichts geöffnet. Für Privatleute ist es kostenlos.

Der Server bekommt eine feste Adresse wie `https://wohnzimmer-pc.tailXXXX.ts.net`. Die steht am Ende der Installation und später im Eltern-Bereich unter „Geräte“.

**Auf dem Server** macht das der Installer. Falls er einen Link zu „HTTPS“ anzeigt:
1. Den Link öffnen (oder [login.tailscale.com/admin/dns](https://login.tailscale.com/admin/dns)).
2. Unten bei **„HTTPS Certificates“** auf **„Enable HTTPS“** klicken. MagicDNS muss an sein (ist es normalerweise).
3. Zurück zum Installer-Fenster, er macht von selbst weiter.

**Auf jedem Tablet und Handy:**
1. Die App **Tailscale** installieren (App Store bzw. Google Play).
2. Öffnen und mit **demselben Konto** anmelden wie am Server.
3. Den Schalter auf **„Connected“** stellen. Er muss an bleiben, solange die Kinder LittleChat benutzen.

> **Häufigster Fehler:** Auf dem Tablet „lädt nichts“. Dann ist Tailscale dort aus, nicht installiert oder mit einem anderen Konto angemeldet.

Später nachholen, falls du Tailscale bei der Installation übersprungen hast: Installer einfach noch einmal starten.

---

## 5. Ersteinrichtung im Browser

Der Installer öffnet den Browser von selbst. Sonst am Server `http://localhost:8787` öffnen.

1. **Einrichtungscode** eingeben (steht im Installer-Fenster und in `data\EINRICHTUNGSCODE.txt`).
2. **Eltern-Passwort** festlegen, mindestens 10 Zeichen. Nicht den Kindern verraten.
3. **API-Schlüssel:** Der Assistent erklärt Schritt für Schritt, wie du bei Anthropic einen Schlüssel anlegst und ein Ausgabenlimit setzt. Einfügen, fertig. Der Server prüft ihn und speichert ihn verschlüsselt. Andere Anbieter (ChatGPT, Gemini, Mistral, Grok, Ollama) gehen später im Eltern-Bereich.
4. **Wiederherstellungsschlüssel** aufschreiben oder ausdrucken und gut aufheben. Ohne ihn lassen sich Backups auf einem neuen Rechner nicht öffnen.
5. Im Eltern-Bereich unter **Kinder** jedes Kind mit Vorname und Geburtsdatum anlegen und die Zeitlimits prüfen (Uhrzeit, Minuten, Fragen).

**Eltern-Bereich öffnen:** Auf dem Startbildschirm das **Zahnrad ⚙ oben rechts 2 Sekunden gedrückt halten**, dann das Eltern-Passwort eingeben. Kurzes Antippen öffnet ihn absichtlich nicht, dann erklärt LittleChat dem Kind nur, dass das Zahnrad für die Eltern ist. Beim Verlassen sperrt sich der Eltern-Bereich wieder.

---

## 6. Tablet koppeln

1. Auf dem Tablet Tailscale einschalten und die Server-Adresse öffnen (`https://….ts.net`, steht im Eltern-Bereich unter „Geräte“).
2. **Als App auf den Home-Bildschirm legen:**
   - iPad/iPhone: in Safari auf „Teilen“ (Quadrat mit Pfeil) › „Zum Home-Bildschirm“.
   - Android: in Chrome auf ⋮ › „App installieren“.
3. LittleChat über das **neue Symbol** öffnen. Wichtig beim iPad: erst auf den Home-Bildschirm legen, dann koppeln.
4. Im Eltern-Bereich (am Rechner oder auf deinem Handy) unter **„Geräte“** auf **„Kopplungscode erzeugen“** tippen und den 6-stelligen Code auf dem Tablet eingeben. Der Code gilt 10 Minuten.
5. Beim ersten Sprechen fragt das Tablet nach dem Mikrofon: **Erlauben**.

Fertig. Die Kinder halten den großen Knopf gedrückt, sprechen, lassen los und hören die Antwort.

---

## 7. Updates

Du musst nichts tun. LittleChat schaut alle 10 Minuten nach einer neuen Version und spielt sie ein, wenn gerade kein Kind spricht (nachts zwischen 2 und 5 Uhr immer).

- Jede Version ist **signiert**. Ohne gültige Signatur wird nichts installiert.
- Eine Version erscheint erst, nachdem sie mindestens 3 Stunden im Alltag ohne Fehler lief.
- Startet eine neue Version nicht, geht LittleChat **von selbst** auf die alte zurück.
- Die laufende Version steht unten im Eltern-Bereich. Das Protokoll steht in `logs\update.log`.

Sofort nachsehen statt zu warten: eine leere Datei namens `update-now` in den Programmordner legen.

---

## 8. Zurück auf die vorige Version

Gefällt dir etwas an einer neuen Version nicht:

- **Windows:** im Programmordner (`C:\LittleChat`) doppelt auf **`LittleChat-zurueck.cmd`** klicken.
- **Linux:** `sudo -u littlechat touch ~/littlechat/rollback-now` (Pfad anpassen, falls woanders entpackt).

Nach etwa 30 Sekunden läuft die vorige Version. Die zurückgenommene Version wird übersprungen. Die **nächste neuere** Version kommt wieder automatisch. Zurück geht immer genau eine Version.

---

## 9. Deinstallieren

- **Windows:** im Programmordner doppelt auf **`LittleChat-entfernen.cmd`** klicken.
- **Linux:** `sudo bash ~/littlechat/scripts/uninstall-linux.sh`

Entfernt werden Autostart und die HTTPS-Freigabe in Tailscale. Dann wirst du gefragt, ob auch **alle Daten** (Kinder, Gespräche, Figuren, Backups, Schlüssel) gelöscht werden sollen. Dafür musst du `LÖSCHEN` eintippen. Sonst bleiben sie, und eine spätere Neuinstallation macht genau dort weiter.

Node.js und Tailscale bleiben unter Windows installiert, weil sie auch anders genutzt werden können. Entfernen über Einstellungen › Apps. Unter Linux wird das mitgebrachte Node.js mit entfernt.

---

## 10. Wenn etwas nicht klappt

| Problem | Lösung |
|---|---|
| Tablet zeigt „Seite nicht erreichbar“ | Tailscale auf dem Tablet an? Gleiches Konto wie am Server? Server an und nicht im Energiesparmodus? |
| Mikrofon geht nicht | Die Adresse muss mit `https://` beginnen. In den Tablet-Einstellungen das Mikrofon für Safari bzw. Chrome erlauben. |
| „Mit keinem KI-Anbieter verbunden“ | Im Eltern-Bereich unter „KI-Anbieter“ den Schlüssel prüfen. Bei Anthropic Guthaben und Limit prüfen. |
| Stimme klingt anders als erwartet | Im Eltern-Bereich unter „Stimme“ Piper wählen. Fehlt Piper, Installer noch einmal starten. |
| Nach einem Stromausfall | Nichts tun. LittleChat startet mit dem Rechner von selbst. Tipp: im BIOS „Nach Stromausfall einschalten“ aktivieren. |
| Neuer Rechner | LittleChat neu installieren, dann ein Backup aus `data\backups\` mit dem Wiederherstellungsschlüssel einspielen. Anleitung in der `README.md` im Paket, Abschnitt „Wiederherstellung“. |
| Etwas anderes | Protokolle: Windows `C:\LittleChat\data\server.log` und `logs\update.log`, Linux `journalctl -u littlechat`. |

---

## Was der Installer aus dem Internet lädt

Nichts davon steckt im LittleChat-Paket. Alles kommt direkt vom Hersteller und steht unter dessen eigener Lizenz (Einzelheiten in `THIRD_PARTY.md` im Paket):

| Was | Wofür | Woher |
|---|---|---|
| Node.js (LTS) | Laufzeit für LittleChat | Windows: winget, sonst nodejs.org (Prüfsumme geprüft). Linux: nodejs.org nach `/opt/littlechat-node` (Prüfsumme geprüft) |
| Abhängigkeiten (Anthropic-SDK) | Verbindung zur KI | npm |
| Piper und deutsche Stimmen | kostenlose, lokale Stimme | GitHub (rhasspy/piper) und Hugging Face, Prüfsumme geprüft |
| Visual-C++-Laufzeit (nur Windows) | braucht Piper | winget, sonst Microsoft |
| Tailscale (wenn gewünscht) | HTTPS für die Tablets | winget bzw. pkgs.tailscale.com, Linux: tailscale.com/install.sh |

Updates von LittleChat selbst kommen nur aus dem Repository [TimoHuebner0815/LittleChat](https://github.com/TimoHuebner0815/LittleChat). Dabei wird nur die Datei `latest.json` abgerufen. Daten über dich oder deine Kinder werden nicht gesendet.

---

## Datenschutz bei Updates

Beim Prüfen auf Updates ruft LittleChat nur `latest.json` aus diesem Repository ab. GitHub sieht dabei wie bei jedem Abruf die IP-Adresse. Daten über dich oder deine Kinder werden nicht gesendet. Jede Version ist mit einem Schlüssel signiert, den nur der Prüfrechner kennt. Ohne gültige Signatur wird nichts installiert. Was LittleChat sonst speichert und an wen es geht, steht in `PRIVACY.md` im Paket.

## Lizenz

Copyright (c) 2026 LittleChat. Alle Rechte vorbehalten. Erlaubt ist nur die private Nutzung im eigenen Haushalt, widerruflich. Einzelheiten in [LICENSE.txt](LICENSE.txt).
