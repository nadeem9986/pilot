# Pilot

A personal AI agent. It is a chat app where the AI does not just talk - it remembers things about you and takes actions for you.

- **Remembers**: tell it a fact once, it still knows it weeks later (stored in a database, not in the chat).
- **Takes actions**: the AI calls real functions (add a todo, save a fact) and decides on its own when to use them.
- **Shows its work**: every action appears as a small card in the chat, so you can see what it did.

Status: Weekend 0 - fresh Next.js scaffold. Nothing agent-related is built yet. See `SEEDFILE.md` for the full plan and current state.

## Stack

| Piece | Choice |
| --- | --- |
| App | Next.js (App Router) + React + TypeScript |
| Backend | Node (Next.js route handlers) |
| Agent brain | LLM API (Claude or OpenAI) through the Vercel AI SDK |
| Database | Postgres on Neon (free tier) |
| Hosting | Vercel (free tier) |

## 6-weekend plan

| Weekend | Goal | Visible result |
| --- | --- | --- |
| 1 | Live streaming chat, deployed | A live URL where you chat with an AI |
| 2 | Save chats, multiple conversations | Chats survive a refresh |
| 3 | Persistent memory | It remembers you across chats |
| 4 | Todos + action cards | It takes actions you can see |
| 5 | Personality, settings, polish (buffer) | It feels finished |
| 6 | Demo video, README, LinkedIn + X post | Public launch |

## Run locally

```bash
npm install
npm run dev
```

Then open http://localhost:3000.

Other commands: `npm run build` (production build), `npm run lint` (check code).
