# 🏢 Health Insurance AI Assistant — ExpressBackend

A robust, scalable Node.js + Express backend that powers authentication, user profile management, and fitness data integration for the Health Insurance AI Assistant platform. This service acts as the secure gateway between the user-facing frontends, the GenAI FastAPI conversational engine, and all ML-driven microservices.

## ✨ Features

- **OAuth2 Authentication**  
  Secure user authentication (mocked Google Fit, easily swappable for Samsung Health/Fitbit).

- **User Profile Management**  
  CRUD operations for user data and health profiles, persisted in MongoDB.

- **Fitness Data Ingestion**  
  Sync and store real-time fitness metrics, ready for ML scoring and insurance personalization.

- **Proxy Layer**  
  Securely forwards enriched requests to the GenAI FastAPI and ML endpoints.

- **JWT-based Authorization**  
  Stateless, scalable security for all protected routes.

- **Production-Ready Logging & Error Handling**  
  Winston-powered logs and robust error middleware.

## 🏗️ Architecture

- **Frontend**: Next.js, React Native
- **Backend**: This Express service
- **GenAI FastAPI**: Conversational & orchestration layer
- **ML Microservices**: Health risk scoring, recommendations

## 📚 API Endpoints

| Method | Path               | Description                          | Auth Required |
|--------|--------------------|--------------------------------------|--------------|
| GET    | `/status`          | Health check                         | No           |
| POST   | `/auth/signup`     | Register new user                    | No           |
| POST   | `/auth/login`      | Obtain JWT token                     | No           |
| GET    | `/fitness/sync`    | Sync (mocked) fitness data           | Yes          |
| GET    | `/profile`         | Get user profile                     | Yes          |
| PUT    | `/profile`         | Update user profile                  | Yes          |
| POST   | `/genai/chat`      | Proxy chat to GenAI FastAPI backend  | Yes          |

## 🛠️ Tech Stack

- **Node.js** & **Express 5**
- **TypeScript** for type safety
- **MongoDB** (Mongoose ODM)
- **Zod** for schema validation
- **Winston** for logging
- **Axios** for HTTP requests

## ⚡ Getting Started

Clone the repository:

```bash
git clone https://github.com/jaynabp/Health-insurance-AI-assistant-ExpressBackend.git
cd Health-insurance-AI-assistant-ExpressBackend
```

Install dependencies:

```bash
npm ci
```

Set up environment variables:

```bash
cp .env.example .env
# Fill in MONGO_URI, JWT_SECRET, GENAI_BASE_URL, etc.
```

Run the development server:

```bash
npm run dev
```

## 🗂️ Project Structure

```
src/
 ├── routes/         # API route definitions
 ├── controllers/    # Request handlers
 ├── models/         # Mongoose schemas
 ├── middleware/     # Auth, error handlers, logging
 ├── services/       # External API and ML service clients
 └── index.ts        # App entrypoint
```

## ⚙️ Configuration

All sensitive configuration is managed via environment variables:

| Variable         | Purpose                               |
|------------------|---------------------------------------|
| `MONGO_URI`      | MongoDB connection string             |
| `JWT_SECRET`     | Secret for JWT signing                |
| `GENAI_BASE_URL` | URL of GenAI FastAPI backend          |
| `PORT`           | Server port (default: 4000)           |

## 🚀 Deployment

**Docker:**

```bash
docker build -t express-backend .
docker run -p 4000:4000 --env-file .env express-backend
```

**Production Tips:**

- Use a managed MongoDB service for reliability.
- Set strong JWT secrets and rotate regularly.
- Monitor with tools like PM2 or Docker Compose.

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome!  
Please open an issue or submit a pull request.

## 📄 License

MIT License © 2025 [jaynabp](https://github.com/jaynabp)

> **Empowering a new era of personalized, preventive, and gamified health insurance — seamlessly connecting your fitness journey to real-world insurance benefits.**

