## 📄 Einheitliches README-Template für jeden Service

Jeder Microservice verwendet folgendes `README.md`-Template:

````md
# ✨ <SERVICE-NAME>

**Teil von [Scriptora](https://github.com/scriptora-ai/scriptora)**  
📦 Microservice für <kurze Beschreibung>

---

## 🔍 Übersicht

| Kategorie          | Wert                          |
|--------------------|-------------------------------|
| Sprache            | Python (FastAPI) / TypeScript (NestJS) |
| Port               | `5XYZ`                        |
| Kommunikation      | REST / GraphQL / gRPC         |
| Datenbank          | z. B. MongoDB, SQLite, JSON   |
| Docker-kompatibel  | ✅                            |
| Status             | MVP / in Entwicklung / Stable |

---

## ⚙️ Setup

### 🐳 Docker (empfohlen)

```bash
docker build -t scriptora/<service-name> .
docker run -p 5XYZ:5XYZ scriptora/<service-name>
````

### 🧑‍💻 Lokaler Start

```bash
# Python
uvicorn src.main:app --host 0.0.0.0 --port 5XYZ --reload

# TypeScript
npm install
npm run start:dev
```

### 🧪 Tests

```bash
# Python
pytest

# TypeScript
npm run test
```

---

## 🚀 API-Dokumentation

### Beispiel: `POST /analyze`

```http
POST /analyze
Content-Type: application/json

{
  "text": "Ich bin traurig"
}
```

**Antwort:**

```json
{
  "emotion": "Trauer",
  "confidence": 0.92
}
```

> Swagger/OpenAPI: [http://localhost:5XYZ/docs](http://localhost:5XYZ/docs)
> GraphQL Playground: [http://localhost:5XYZ/graphql](http://localhost:5XYZ/graphql)

---

## 🔐 Authentifizierung

* ⛔ Nicht erforderlich für MVP
* 🔐 Optional: Keycloak JWT-Token-Unterstützung

---

## 📁 Projektstruktur

```
.
├── src/
│   ├── main.py
│   ├── api/
│   ├── services/
│   └── models/
├── tests/
├── Dockerfile
├── requirements.txt / package.json
└── README.md
```

---

## 🔄 CI/CD

Beispiel `.github/workflows/ci.yml`:

```yaml
name: CI
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Setup
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      - run: pip install -r requirements.txt
      - run: pytest
```

Oder bei TypeScript:

```yaml
      - uses: actions/setup-node@v3
        with:
          node-version: '20'
      - run: npm ci
      - run: npm run test
```

---

## 🔗 Verbundene Services

Dieser Service wird hauptsächlich verwendet von:

* `voice-command-gateway`
* `scriptora-app`

---

## 🧠 Lizenz & Mitwirken

Open Source unter [GPL-3.0 License](./LICENSE)
Mitwirken? Pull Request willkommen oder Kontakt über [Scriptora](https://github.com/scriptora-ai/scriptora)
