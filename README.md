# LittleChat

**Ein Walkie-Talkie für Kinder, mit dem sie per Stimme Fragen an eine KI stellen: standardmäßig Claude, wahlweise ChatGPT, Gemini, Mistral, Grok oder lokal über Ollama.** Knopf gedrückt halten, fragen, loslassen, Antwort hören. Eltern bestimmen Limits, geben Geräte frei und können die Gespräche nachlesen.

> Inoffiziell, nicht mit Anthropic, OpenAI, Google, Mistral AI, xAI oder Ollama verbunden. „Claude“, „ChatGPT“, „Gemini“ und „Grok“ sind Marken ihrer Anbieter. LittleChat nutzt die öffentlichen APIs mit deinem eigenen API-Schlüssel. Ein Abo (Claude Pro, ChatGPT Plus …) funktioniert nicht.

## KI-Anbieter

Claude ist der Standard und für Kinder am besten abgestimmt. Im Eltern-Bereich lassen sich weitere Anbieter einrichten, global oder pro Kind: ChatGPT (OpenAI), Gemini (Google), Mistral (Daten in der EU), Grok (xAI) und Ollama (lokal, kostenlos, auf schwacher Hardware langsam). Alle Anbieter außer Claude sind mit der Persona von LittleChat **ungetestet**. Anleitungen pro Anbieter sind im Eltern-Bereich verlinkt.

## Verantwortung der Eltern

**Eltern tragen die Verantwortung für die Nutzung durch ihre Kinder und haften für sie im Rahmen ihrer Aufsichtspflicht.** Behaltet die Themen und Gespräche im Blick, im Eltern-Bereich lässt sich jedes Gespräch nachlesen. Keine KI ist fehlerfrei. **Nutzung auf eigene Gefahr.**

Dieses Repository enthält nur die **fertigen, signierten Pakete**. Der Quellcode ist nicht öffentlich.

## Installieren (Windows)

1. [Neueste Version herunterladen](https://github.com/TimoHuebner0815/LittleChat/raw/main/releases/littlechat-latest.zip) und entpacken, z. B. nach `C:\LittleChat`.
2. Im Ordner mit der rechten Maustaste auf `scripts\install-windows.ps1` klicken und **„Mit PowerShell ausführen“** wählen.
3. Das Skript richtet alles ein, auch die automatischen Updates, und öffnet den Einrichtungs-Assistenten im Browser.

Die vollständige Anleitung steht in der `README.md` im Paket.

## Updates

Eine installierte LittleChat holt neue Versionen von hier selbst ab:

- **Signiert:** Jede Version ist mit einem Schlüssel signiert, den nur der Prüfrechner kennt. Ohne gültige Signatur wird nichts installiert.
- **Erprobt:** Eine Version erscheint hier erst, nachdem sie mindestens 12 Stunden ohne Fehler im Alltag lief.
- **Rücksichtsvoll:** Eingespielt wird nur, wenn gerade kein Kind spricht. Startet die neue Version nicht, kehrt LittleChat automatisch zur alten zurück.
- **Privat:** Beim Prüfen auf Updates ruft LittleChat nur `latest.json` von GitHub ab. GitHub sieht dabei wie bei jedem Abruf die IP-Adresse. Daten über dich oder deine Kinder werden nicht gesendet.

## Lizenz

Copyright (c) 2026 Timo Hübner / LittleClaude. Alle Rechte vorbehalten. Erlaubt ist nur die private Nutzung im eigenen Haushalt, Einzelheiten in [LICENSE.txt](LICENSE.txt).
