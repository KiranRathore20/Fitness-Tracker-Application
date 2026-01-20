# 🏋️‍♂️ Fitness Tracker Application

An **AI-powered fitness tracking application** built with **Java Spring Boot** (backend) and **React** (frontend) using a scalable **microservices architecture**. The project includes secure authentication, service discovery, centralized config, event-driven messaging, and personalized AI fitness insights.

## 🚀 Features
- 🤖 **AI-Powered Insights** — Uses Gemini API for fitness recommendations and predictions  
- 🔐 **Secure Authentication** — Keycloak for OAuth2 / OIDC authentication & authorization  
- 📡 **Service Discovery** — Eureka Server for automatic microservice registration  
- 📨 **Event-Driven Messaging** — RabbitMQ for asynchronous communication  
- 🗄️ **MongoDB Database** — Persistence layer for user & fitness data  
- ⚙️ **Centralized Config** — Spring Cloud Config Server  
- 🌐 **React Frontend** — Responsive UI for user interaction-
- 
## 🛠️ Tech Stack
### Backend
- Java 17+
- Spring Boot
- Spring Cloud (Eureka, Config Server)
- RabbitMQ
- MongoDB
- Keycloak
- Gemini API

### Frontend
- React
- Axios

Make sure the following software is installed:
✔ Java 17+  
✔ Node.js 18+  
✔ MongoDB  
✔ RabbitMQ  
✔ Keycloak  
✔ Maven  
✔ Git  
## 🧰 Setup Instructions

### 1. Clone the repository
git clone https://github.com/KiranRathore20/Fitness-Tracker-Application.git
cd Fitness-Tracker-Application
Backend Setup

Navigate to backend folder:

cd fitness-backend


Build the project:

mvn clean install -DskipTests


Run the backend:

mvn spring-boot:run

🖥️ Frontend Setup

Navigate to frontend folder:

cd fitness-frontend


Install dependencies:

npm install


Start the frontend:

npm start

🔐 Environment Variables
Frontend .env

Create a .env file inside the frontend folder:

REACT_APP_API_BASE_URL=http://localhost:8080
REACT_APP_KEYCLOAK_URL=http://localhost:8081
REACT_APP_GEMINI_API_KEY=<YOUR_GEMINI_API_KEY>

Backend application.yml (or .env)

Add or update these values:

spring.data.mongodb.uri=mongodb://localhost:27017/fitness
spring.rabbitmq.host=localhost

keycloak.auth-server-url=http://localhost:8081
keycloak.realm=your-realm
keycloak.resource=your-client-id

gemini.api.key=<YOUR_GEMINI_API_KEY>

🧱 Architecture Overview
 ┌────────────────────────────────────────────────────────────┐
 │                        React Frontend                      │
 └─────────────▲──────────────────────────────────────────────┘
               │ REST / OAuth2
               ▼
 ┌─────────────────────┐    Event Bus     ┌─────────────────────┐
 │ Fitness Service     │◀───────────────▶ │ Analytics Service   │
 └─────────────────────┘                  └─────────────────────┘
             │ MongoDB                          │ Gemini AI
             ▼                                   ▼
 ┌─────────────────────┐                  ┌─────────────────────┐
 │  Eureka Server      │   Config via     │ Config Server       │
 └─────────────────────┘◀────────────────▶└─────────────────────┘
                                   │
                             RabbitMQ Broker
                                   │
                             Keycloak Server

🧪 Testing

You can add automated tests in the backend and frontend to validate endpoints and UI functionality.


