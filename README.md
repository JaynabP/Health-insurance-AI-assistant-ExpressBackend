A Node.js + Express façade that handles authentication, user profile storage, and fitness-data ingestion before forwarding enriched payloads to the GenAI FastAPI layer and ML services.

What it does

OAuth (mocked Google Fit → easy swap for Samsung Health / Fitbit).

REST-style user CRUD and JWT auth.

Proxy routes (/genai/*) with circuit-breaker logic.

MongoDB (or any Mongoose-compatible store) for persisting health-profile snapshots.

Running locally

bash
git clone https://github.com/jaynabP/health-insurance-AI-assistant-ExpressBackend.git
cd health-insurance-AI-assistant-ExpressBackend
npm ci          # locks versions via package-lock.json
cp .env.example .env   # add MONGO_URI, JWT_SECRET, GENAI_BASE_URL
npm run dev     # nodemon hot reload
Notable routes

Method	Path	Description
GET	/status	Health check
POST	/auth/signup	Email + password sign-up
POST	/auth/login	Obtain JWT
GET	/fitness/sync	Fetch (mocked) fitness metrics
POST	/genai/chat	Proxy to FastAPI /chat
Tech stack

Express 5, TypeScript, Zod schema validation

Mongoose (MongoDB 6+)

Axios, Node-cache, Winston logging

MIT License.