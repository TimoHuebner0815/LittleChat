# LittleChat

**Ein Walkie-Talkie für Kinder, mit dem sie per Stimme Fragen an eine KI stellen: standardmäßig Claude, wahlweise ChatGPT, Gemini, Mistral, Grok oder lokal über Ollama.** Knopf gedrückt halten, fragen, loslassen, Antwort hören. Eltern bestimmen Limits, geben Geräte frei und können die Gespräche nachlesen.

> Inoffiziell, nicht mit Anthropic, OpenAI, Google, Mistral AI, xAI oder Ollama verbunden. „Claude“, „ChatGPT“, „Gemini“ und „Grok“ sind Marken ihrer Anbieter. LittleChat nutzt die öffentlichen APIs mit deinem eigenen API-Schlüssel. Ein Abo (Claude Pro, ChatGPT Plus …) funktioniert nicht.

## Was LittleChat kann

- **Nur Sprache:** Kinder brauchen nicht lesen zu können. Bis 8 Jahre wird jeder Knopf angesagt, Untertitel zeigen den vorgelesenen Satz (pro Kind abschaltbar).
- **Fünf Gesprächsmodi:** Lernen, Erkunden, Erforschen, Kreativ, Langeweile, pro Kind freischaltbar. Im Kreativ-Modus erfindet das Kind bis zu 3 eigene Avatare als Profilbild.
- **Seifenblasen:** Frühere Gespräche schweben als Blasen über den Bildschirm, Antippen setzt sie fort.
- **Eigene Farbe** wählt jedes Kind selbst, ein Farbschloss schützt das Profil vor Geschwistern.
- **Stimmen:** Piper lokal und kostenlos (Standard), wahlweise Google, Microsoft Azure, ElevenLabs oder die Stimme des Geräts, für alle oder pro Kind.
- **Eltern-Bereich:** Limits (Uhrzeit, Minuten, Fragen, Tokens, Dollar), Gespräche nachlesen und löschen, Geräte freigeben, Name des Assistenten ändern.

## KI-Anbieter

Claude ist der Standard und für Kinder am besten abgestimmt. Im Eltern-Bereich lassen sich weitere Anbieter einrichten, global oder pro Kind: ChatGPT (OpenAI), Gemini (Google), Mistral (Daten in der EU), Grok (xAI) und Ollama (lokal, kostenlos, auf schwacher Hardware langsam). Alle Anbieter außer Claude sind mit der Persona von LittleChat **ungetestet**. Anleitungen pro Anbieter sind im Eltern-Bereich verlinkt.

## Verantwortung der Eltern

**Eltern tragen die Verantwortung für die Nutzung durch ihre Kinder und haften für sie im Rahmen ihrer Aufsichtspflicht.** Behaltet die Themen und Gespräche im Blick, im Eltern-Bereich lässt sich jedes Gespräch nachlesen. Keine KI ist fehlerfrei. **Nutzung auf eigene Gefahr.**

Dieses Repository enthält nur die **fertigen, signierten Pakete**. Der Quellcode ist nicht öffentlich.

## Installieren

Alles, was LittleChat braucht (Node.js, Stimmen, Tailscale für die Tablets), lädt der Installer selbst vom jeweiligen Hersteller. Du brauchst nur einen Rechner, der an bleibt, einen API-Schlüssel (z. B. von Anthropic) und ein kostenloses Tailscale-Konto. Dauer: etwa 30 Minuten.

**Windows 10/11**
1. [littlechat-latest.zip herunterladen](https://github.com/TimoHuebner0815/LittleChat/raw/main/releases/littlechat-latest.zip) und entpacken (Rechtsklick › „Alle extrahieren…“).
2. Im Ordner doppelt auf **`LittleChat-installieren.cmd`** klicken und die Fragen mit Enter bestätigen.
3. Im Browser, der sich öffnet, den Einrichtungscode eingeben, Eltern-Passwort und API-Schlüssel festlegen.

**Linux / Raspberry Pi (64 Bit)**
```bash
curl -fsSLO https://github.com/TimoHuebner0815/LittleChat/raw/main/releases/littlechat-latest.zip
mkdir -p ~/littlechat && cd ~/littlechat && unzip -o ../littlechat-latest.zip
sudo bash scripts/install-linux.sh
```

**Tablets:** App **Tailscale** installieren und mit demselben Konto anmelden, die angezeigte `https://….ts.net`-Adresse öffnen, zum Home-Bildschirm hinzufügen und im Eltern-Bereich unter „Geräte“ koppeln.

Die ausführliche, bebilderte Schritt-für-Schritt-Anleitung (auch Zurück auf die vorige Version, Deinstallieren, Probleme lösen) steht in **`INSTALLATION.md`** im Paket.

## Updates

Eine installierte LittleChat holt neue Versionen von hier selbst ab:

- **Signiert:** Jede Version ist mit einem Schlüssel signiert, den nur der Prüfrechner kennt. Ohne gültige Signatur wird nichts installiert.
- **Erprobt:** Eine Version erscheint hier erst, nachdem sie mindestens 3 Stunden ohne Fehler im Alltag lief.
- **Rücksichtsvoll:** Eingespielt wird nur, wenn gerade kein Kind spricht. Startet die neue Version nicht, kehrt LittleChat automatisch zur alten zurück. Von Hand zurück geht mit `LittleChat-zurueck.cmd` (Windows).
- **Privat:** Beim Prüfen auf Updates ruft LittleChat nur `latest.json` von GitHub ab. GitHub sieht dabei wie bei jedem Abruf die IP-Adresse. Daten über dich oder deine Kinder werden nicht gesendet.

## Lizenz

Copyright (c) 2026 LittleChat. Alle Rechte vorbehalten. Erlaubt ist nur die private Nutzung im eigenen Haushalt, Einzelheiten in [LICENSE.txt](LICENSE.txt).
