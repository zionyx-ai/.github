# 📖 Scriptora – Das lebendige Wort in deiner Stimme

**Organisation:** `scriptora-ai`
**Vision:** Worte, die heilen. Stimmen, die leiten.
**Mission:** Glaube, Sprache und KI in Einklang bringen.

Scriptora ist eine spirituell orientierte Plattform für KI-gestützte Sprach- und Textsysteme, die Menschen auf ihrem geistlichen und emotionalen Weg begleiten. Die App erkennt gesprochene Begriffe wie biblische Namen (z. B. „Caleb“), konkrete Stellen („Genesis 1, Vers 1“) oder emotionale Aussagen (z. B. „Ich bin traurig“) und gibt daraufhin passende Bibelverse zurück. Im Zentrum steht die seelsorgerliche Unterstützung durch KI.

---

## 🌟 Features im MVP

1. 🎙️ Spracheingabe → Bibelvers (z. B. „Genesis 1 Vers 1“)
2. 🧠 Stichwort → relevante Verse (z. B. „Caleb“)
3. ❤️ Emotion → Trostvers (z. B. bei „Ich bin traurig“)

---

## 🧩 Microservice-Architektur

| Service-Name               | Beschreibung                                 | Sprache                | Datenbank        | Port |
| -------------------------- | -------------------------------------------- | ---------------------- | ---------------- | ---- |
| `speech-to-text-service`   | Sprachaufnahme → Text (Whisper etc.)         | Python                 | —                | 5100 |
| `bible-lookup-service`     | Findet Verse zu konkreten Stellen            | Python                 | JSON/SQLite      | 5200 |
| `bible-keyword-service`    | Biblische Stellen zu Namen & Begriffen       | Python                 | JSON/SQLite      | 5300 |
| `emotion-analysis-service` | NLP-Analyse von Stimmung (Trauer, Wut, etc.) | Python                 | —                | 5400 |
| `encouragement-service`    | Liefert passende Mutmach-/Trostverse         | Python                 | MongoDB (später) | 5500 |
| `voice-command-gateway`    | Zentraler Gateway zur Befehlsverarbeitung    | TypeScript             | —                | 5000 |
| `scriptora-app`            | Mobile/Web-App für Benutzer\:innen           | Flutter / React Native | lokal            | 5600 |

---

## 🧪 Technologie-Stack

* **Backend:** Python (FastAPI), TypeScript (NestJS)
* **Frontend:** Flutter oder React Native
* **Spracherkennung:** Whisper, Google STT
* **Textanalyse:** spaCy, OpenAI GPT
* **Emotionserkennung:** Regelbasiert + ML/NLP-Klassifikation
* **Speicherung:** JSON, SQLite, MongoDB, Cloud (Supabase)
* **Kommunikation:** REST, GraphQL, gRPC (optional)
* **CI/CD:** GitHub Actions, Docker, ggf. Kubernetes

---

## 📦 Port-Konvention

| Bereich                | Portbereich | Beispiel-Service           |
| ---------------------- | ----------- | -------------------------- |
| Gateway/API            | 5000–5099   | `voice-command-gateway`    |
| Speech/Text-Input      | 5100–5199   | `speech-to-text-service`   |
| Bibel-Lookup           | 5200–5299   | `bible-lookup-service`     |
| Keyword-Analyse        | 5300–5399   | `bible-keyword-service`    |
| Emotion & Sentiment    | 5400–5499   | `emotion-analysis-service` |
| Seelsorge & Ermutigung | 5500–5599   | `encouragement-service`    |
| App/API Frontend       | 5600–5699   | `scriptora-app`            |

---

## 🎨 Branding

**Farbschema (empfohlen):**

| Kategorie     | Hex       | Beschreibung             |
| ------------- | --------- | ------------------------ |
| Primärfarbe   | `#3B2F63` | Geistliches Violett      |
| Sekundärfarbe | `#A58FD1` | Sanftes Lavendel         |
| Akzentfarbe   | `#FFD166` | Hoffnungsvoll (Goldgelb) |
| Neutralfarbe  | `#F5F5F5` | Hintergrund/Weiß         |

---

## 📂 Repository-Struktur

Alle Services leben in ihrer eigenen Codebasis in `zionyx-ai` bzw. `scriptora-ai`:

```
github.com/zionyx-ai/speech-to-text-service
github.com/zionyx-ai/bible-lookup-service
github.com/zionyx-ai/bible-keyword-service
github.com/zionyx-ai/emotion-analysis-service
github.com/zionyx-ai/encouragement-service
github.com/zionyx-ai/voice-command-gateway
github.com/scriptora-ai/scriptora-app
github.com/scriptora-ai/scriptora         # Zentrale Doku, Planung, Vision
```

---

## 🚀 Roadmap

* [ ] Organisation `scriptora-ai` gründen
* [ ] Wunschdomain registrieren: `scriptora.app` oder `scriptora.ai`
* [ ] Repositories initialisieren mit Basisstruktur (README, Dockerfile, main.py/...)
* [ ] MVP-Funktionalitäten umsetzen
* [ ] CI/CD für alle Services einrichten (Docker, GitHub Actions)
* [ ] Logo & Branding Assets gestalten
* [ ] App-Prototyp erstellen (Flutter/React Native)

---

## 📞 Kontakt

**Scriptora – das lebendige Wort in deiner Stimme.**
Anfragen, Feedback oder geistlich motivierte Kooperationen sind willkommen.

---
