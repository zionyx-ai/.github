# 🚀 Anleitung: Scriptora starten (für Einsteiger\:innen auf Windows)

Willkommen! In dieser Anleitung erfährst du, wie du Scriptora – eine KI-basierte Bibel-App – lokal auf deinem Windows-PC startest. Schritt für Schritt.

---

## 📅 1. Repositories klonen oder herunterladen

### ✅ Option 1: GitHub Desktop (empfohlen)

1. Installiere [GitHub Desktop](https://desktop.github.com/)
2. Klicke auf „File → Clone Repository…“
3. Suche nach `scriptora-ai/scriptora`
4. Wiederhole das für alle benötigten Repositories, z. B.:

* `scriptora-ai/scriptora`
* `scriptora-ai/gateway`
* `scriptora-ai/analyze`
* `scriptora-ai/lookup`
* `scriptora-ai/transcribe`
* `scriptora-ai/relate`
* `scriptora-ai/chatbox`

### 📆 Option 2: ZIP-Dateien herunterladen

1. Öffne [https://github.com/scriptora-ai](https://github.com/scriptora-ai)
2. Klicke auf jedes Repository → „Code“ → „Download ZIP“
3. Entpacke jede ZIP-Datei an einen passenden Ort, z. B. `C:\Users\DeinName\scriptora`

---

## 📆 2. Projektordner öffnen

Öffne den Hauptordner, der alle entpackten oder geklonten Repositories enthält
(z. B. `scriptora`, `gateway`, `lookup`, `chatbox`, etc.)

---

## 🧱 3. Datenbank & KI-Backend starten (PostgreSQL + Ollama)

1. Öffne **PowerShell** oder **Windows-Terminal**
2. Gehe in den Ordner `compose/postgres`:

```powershell
cd pfad/zum/Ordner/scriptora/compose/postgres
```

(Beispiel: `cd C:\Users\DeinName\Downloads\scriptora\compose\postgres`)

3. Starte PostgreSQL **und** Ollama:

```powershell
docker compose up -d
```

---

## 🧠 4. Python/TypeScript-Microservices starten

### Neue Microservices liegen nun unter `/services`. Wiederhole folgende Schritte pro Service:

### Schritte:

1. Gehe im Terminal in den jeweiligen Service-Ordner, z. B.:

```powershell
cd C:\Users\DeinName\Downloads\scriptora\services\analyze
```

2. Aktiviere die virtuelle Umgebung (nur bei Python-Services):

```powershell
. .venv\Scripts\Activate.ps1
```

3. Installiere Abhängigkeiten:

```powershell
uv sync --all-groups
```

4. Starte den Service:

```powershell
uv run analyze
```

### Wiederhole das für folgende Services:

* `analyze`
* `gateway`
* `lookup`
* `relate`
* `transcribe`
* `chatbox`

⚠️ **Wichtig:** Immer im jeweiligen Ordner im Terminal sein!

---

## 💻 5. Frontend starten

1. Gehe in den Ordner `frontend`
2. Installiere die Abhängigkeiten:

```powershell
npm install
```

3. Starte das Frontend:

```powershell
npm run dev
```

4. Öffne deinen Browser:
   👉 [http://localhost:3000](http://localhost:3000)

---

## 🧪 6. Tests, Ground Truth & Dashboard

### Was ist „Ground Truth“?

Ground Truth = die echte, richtige Text-Version eines Satzes – notwendig für Qualitätsmessung bei Sprache-zu-Text.

### Audio-Dateien erzeugen

```powershell
uv run generate-audio
```

### Ground Truth erzeugen

```powershell
uv run generate-stt-gt
```

### Test-Dashboard öffnen

```powershell
uv run dashboard
```

Dann im Browser öffnen: 👉 [http://localhost:8501](http://localhost:8501)

---

Viel Erfolg und Segen beim Ausprobieren von Scriptora!
