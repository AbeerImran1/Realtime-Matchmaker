# Real-Time Matchmaking Service
A scalable, real-time matchmaking backend designed for multiplayer games. Players join a queue, are matched based on skill (MMR), and are notified instantly via WebSockets.

## Tech Stack
- **Backend:** Node.js, TypeScript, Socket.IO
- **Database:** MySQL (Amazon RDS)
- **Hosting:** AWS ECS Fargate, Application Load Balancer
- **CI/CD:** Docker, GitHub Actions, Amazon ECR

## Architecture
- **Client:** React (WebSocket client)
- **Matchmaking Logic:** In-memory priority queue based on expanding MMR thresholds.
- **Database:** Stores persistent player stats, match history, and event logs.

## Roadmap

### Phase 1: Local MVP
- [ ] Initialize Node.js/TypeScript project.
- [ ] Set up Docker Compose for local MySQL database.
- [ ] Implement basic player authentication (JWT or session).
- [ ] Write the core matchmaking algorithm (expanding MMR threshold).

### Phase 2: Real-Time Layer
- [ ] Integrate Socket.IO for real-time communication.
- [ ] Implement `join_queue`, `leave_queue`, and `match_found` events.
- [ ] Handle edge cases (player disconnects while queued, reconnect logic).

### Phase 3: Containerization & AWS
- [ ] Write multi-stage `Dockerfile` for the backend.
- [ ] Provision Amazon ECR repository and push the image.
- [ ] Set up Amazon RDS for MySQL.
- [ ] Provision ECS Fargate cluster and Application Load Balancer.
- [ ] Configure GitHub Actions to build and deploy to ECS on push to `main`.

### Phase 4: Performance & Polish
- [ ] Write integration tests using Vitest/Jest.
- [ ] Create a load-testing script (Artillery or k6) to simulate 100+ concurrent players.
- [ ] Document p95 time-to-match and system throughput in README.
