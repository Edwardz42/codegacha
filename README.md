# codeGacha
 
**A competitive 1v1 quiz game where players collect computer-science questions from gacha packs and battle by answering each other's decks — with free-text answers graded by semantic search.**
 
Built at **UniHack 2026**.
 
**[Live demo →](https://codegacha-frontend.vercel.app)**
 
<img width="1708" alt="codeGacha screenshot" src="https://github.com/user-attachments/assets/ea3a8c41-dc86-4db7-a8e6-baa5ac5602b9" />

## Features

- **Gacha packs** with a 3D opening animation in Three.js. Each pack holds 8 question cards weighted by rarity (easy, medium or hard).
- **Deckbuilding.** Players pick 8 of their collected cards to bring into battle.
- **Real-time 1v1 rooms** with invite codes. Each player answers their opponent's deck against a 10-minute clock.
- **AI answer grading.** Free-text answers are scored by meaning rather than exact wording.
- **Scoring system** with points for difficulty, speed and answer streaks, plus a leaderboard.

## Technical highlights

- **Semantic answer grading:** answers are embedded and compared to an ideal answer with an Elasticsearch kNN vector search. That score is blended with keyword coverage, and vague answers are capped low.
- **Server-side game engine:** a REST API manages each match from start to finish, including room creation, readiness checks, scoring, and breaking tied scores by total answer time.
- **Layered backend:** an Express API organised into routes, controllers, services and an engine, deployed on Render.

## Tech stack

**Frontend:** React, Vite, Three.js
**Backend:** Node.js, Express
**Search / AI:** Elasticsearch Cloud (vector search with text embeddings)
**Deployment:** Render

## Run locally

```bash
# Backend (needs Elasticsearch credentials in backend/src/.env)
cd backend && npm install && npm run dev

# Frontend
cd frontend && npm install && npm run dev
```

## License

MIT
