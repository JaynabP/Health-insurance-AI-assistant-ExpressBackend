🏢 Health Insurance AI Assistant — Express Backend
A robust Node.js + Express backend that manages authentication, user profiles, and fitness data ingestion for the AI-powered insurance platform. This service acts as the “gateway” to the GenAI and ML microservices, ensuring secure, scalable, and reliable data flow.

🌟 Features
OAuth2 Authentication: (Mocked Google Fit, swappable for Samsung Health/Fitbit)

User Profiles: CRUD operations with MongoDB.

Fitness Data Sync: Ingests and enriches real-time health metrics.

Proxy Layer: Securely forwards requests to GenAI FastAPI and ML endpoints.

JWT Auth: Stateless, scalable security.

🏗️ Tech Stack
Express 5 + TypeScript

MongoDB (via Mongoose)

Zod for schema validation

Winston logging, Axios for HTTP

🚦 API Endpoints
Method	Path	Description
GET	/status	Service health check
POST	/auth/signup	Register new user
POST	/auth/login	Obtain JWT
GET	/fitness/sync	Sync (mocked) fitness data
POST	/genai/chat	Proxy chat to FastAPI backend
⚡ Quickstart
bash
git clone https://github.com/JaynabP/Health-insurance-AI-assistant-ExpressBackend.git
cd Health-insurance-AI-assistant-ExpressBackend
npm ci
cp .env.example .env  # Set MONGO_URI, JWT_SECRET, GENAI_BASE_URL
npm run dev
🗂️ Folder Structure
text
src/
 ├── routes/
 ├── controllers/
 ├── models/
 ├── middleware/
 └── index.ts
🛠️ Deployment
bash
docker build -t express-backend .
docker run -p 4000:4000 --env-file .env express-backend
📄 License
MIT — Contributions and feedback welcome!
