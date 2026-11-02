
# Movie Recommendation System

A full-stack movie recommendation web application that suggests movies based on user preferences using modern web technologies and ML-inspired logic. Built for scalability, clean UI, and real-world deployment.

---

## Overview

This project delivers personalized movie recommendations by combining user input, filtering logic, and dynamic movie metadata. The system is designed with a modular frontend, serverless backend, and production-ready deployment pipeline.

---

## Features

- Personalized movie recommendations based on user preferences
- Dynamic movie metadata including posters, descriptions, and ratings
- Responsive and minimal user interface
- Scalable backend using serverless architecture
- Secure authentication and data storage
- Production-ready deployment

---

## Architecture

Frontend:
- Handles user interaction, preference input, and result rendering
- Built for responsiveness and performance

Backend:
- Manages authentication, data storage, and recommendation logic
- Designed to scale without manual server management

Deployment:
- Optimized for fast builds and global delivery

---

## Recommendation Flow

1. User provides preferences such as genre or interests
2. Recommendation logic filters and ranks relevant movies
3. Movie metadata is fetched and mapped to recommendations
4. Results are rendered in the UI in real time

---

## Tech Stack

Frontend:
- Next.js
- React
- Tailwind CSS
- JavaScript

Backend & Machine Learning:
- Content-Based TF-IDF Cosine Similarity ML Engine
- Pre-trained Movie Recommendation Vector Model
- Firebase Authentication & Firestore (Optional)
- TMDB API Integration (Optional)

DevOps & CI/CD:
- Docker (Multi-stage production build)
- Docker Compose
- Jenkins Declarative Pipeline (Automated Lint, Build, Container Health Testing, and Deployment)

---

## Docker & Containerization

### Quick Start with Docker

Build and run the container locally:

```bash
# 1. Build the Docker image
docker build -t movie-recommender:latest .

# 2. Run container on port 3000
docker run -d --name movie-recommender-app -p 3000:3000 --restart unless-stopped movie-recommender:latest

# 3. Check container logs
docker logs -f movie-recommender-app

# 4. Verify health check
curl http://localhost:3000/api/model-info
```

### Quick Start with Docker Compose

```bash
# Start in detached mode
docker compose up -d

# Check status
docker compose ps

# View real-time logs
docker compose logs -f

# Stop and remove containers
docker compose down
```

---

## Jenkins CI/CD Pipeline

The project includes an enterprise-grade `Jenkinsfile` featuring:
1. **SCM Checkout**: Clones the repository and verifies branch status.
2. **Lint & Validation**: Inspects critical files, dependencies, and validates ML recommendation JSON model integrity.
3. **Docker Build**: Builds tagged production images (`movie-recommender:${BUILD_NUMBER}` and `latest`).
4. **Docker Container Health Test**: Spawns an ephemeral test container and asserts health response via `/api/model-info`.
5. **Deploy**: Restarts and serves the verified container on production port `3000`.
6. **Post-Build Cleanup**: Automatically cleans up temporary resources and delivers build status.

---

## Project Structure

```
movie-recommender/
│── components/            Reusable UI components (FilterBar, MovieRecommender, etc.)
│── pages/                 Next.js pages & API routes (recommend, search, trending)
│── public/models/         Pre-trained ML recommendation model data
│── lib/                   Firebase, TMDB, and Watchlist helper utilities
│── styles/                Global and Tailwind styles
│── Dockerfile             Multi-stage production container build
│── docker-compose.yml     Docker Compose service configuration
│── Jenkinsfile            Automated Jenkins CI/CD Pipeline
│── .dockerignore          Docker build ignore rules
│── README.md
```

movie-recommender/
│── components/        Reusable UI components
│── pages/             Next.js pages and routing
│── public/            Static assets
│── firebase/          Firebase configuration
│── utils/             Helper functions and recommendation logic
│── styles/            Global and component-level styles
│── README.md

````

---

## Installation

Clone the repository:

```bash
git clone https://github.com/Arjunyadavsoma/movie-recommender.git
cd movie-recommender
````

Install dependencies:

```bash
npm install
```

Run the development server:

```bash
npm run dev
```

---

## Environment Variables

Create a `.env.local` file and add the following:

```
NEXT_PUBLIC_FIREBASE_API_KEY=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_PROJECT_ID=
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=
NEXT_PUBLIC_FIREBASE_APP_ID=
```

---

## Deployment

The application can be deployed using Vercel or Firebase Hosting. Ensure environment variables are configured in the deployment platform.

---

## Future Enhancements

* Advanced machine learning recommendation models
* Collaborative filtering using user behavior
* Rating and feedback-based learning
* User profiles with watch history
* Analytics for recommendation performance

---

## Repository

GitHub:
- CI/CD & Docker: [ajaychintoo04-art/movie-recommender](https://github.com/ajaychintoo04-art/movie-recommender)
- Upstream: [Arjunyadavsoma/movie-recommender](https://github.com/Arjunyadavsoma/movie-recommender)

---

## Author & Maintainers

- **Original Author**: Soma Arjun Yadav (B.Tech in AI and Machine Learning)
- **DevOps, Docker & Jenkins CI/CD**: Ajay kumar (<Ajaychintoo04@gmail.com>)


