# SEEDFILE - Pilot

Full context for any AI (or human) working on this repo. Read this first.

## Who and why

- Owner: Nadeem (GitHub: nadeem9986), software engineer in Bengaluru, about 8 months of experience. Frontend-leaning: React, Next.js, Node, HTML/CSS/JS. Strong with AI tools. ESP32 hardware hobbyist.
- Build time: weekends only. Saturday about 8:30 AM - 1:30 PM IST, Sunday about 2:00 - 4:30 PM IST.
- Goal: a hire-proof flagship project for agentic-AI companies. Primary target: Instinct, a company that builds a personal AI agent (chat interface, tool use, memory, integrations like email/calendar/messaging, acting on the user's behalf). Pilot is a small, real version of that idea.
- Rule of thumb: build things that look like the target company's product, and ship them live.

## What Pilot is

A chat app where the AI does things. It remembers facts about the user across sessions, keeps a todo list, and takes actions when asked.

## The 3 agent features (these are the point)

1. **Persistent memory.** The user says "my favorite editor is VS Code". Weeks later the agent still knows. Stored in Postgres, not in chat history.
2. **Tool use.** The model calls real functions, for example `add_todo("buy ESP32 board")` and `remember_fact("I work at SmiRox")`. The model decides on its own when to call them.
3. **Visible action cards.** Each tool call shows in the chat as a small card ("Added todo: buy ESP32 board"), so the user can see the agent working.

Stretch goal: a tool that toggles an LED on an ESP32 through an API, so the agent touches the physical world.

## Stack and why

- **Next.js (App Router) + React + TypeScript**: Nadeem's existing comfort zone. Route handlers act as the Node backend.
- **Vercel AI SDK**: handles streaming chat and tool calling. The one new thing to learn. Well documented.
- **LLM API (Claude or OpenAI)**: the agent brain. About $5 of credits covers the whole build.
- **Neon Postgres (free tier)**: stores conversations, messages, memories, todos.
- **Vercel (free tier)**: live deployment. Nadeem likes shipping live sites.

## Weekend milestones

Each weekend must end with something visible.

- **Weekend 1 - Live chat.** Sat: wire up the Vercel AI SDK, get streaming replies working. Sun: clean UI, deploy to Vercel. Visible: a live URL with a working AI chat.
- **Weekend 2 - Chats that survive refresh.** Add Neon Postgres, save messages, support multiple conversations. Visible: refresh the page and the chat is still there.
- **Weekend 3 - Memory.** Add `remember_fact`, store facts in the database, feed them into the agent's context in every new chat. Visible: tell it something, open a new chat, it knows.
- **Weekend 4 - Todos and action cards.** Add `add_todo` / `list_todos` / `complete_todo` and show each tool call as an action card. Visible: the agent takes actions you can see.
- **Weekend 5 - Polish (buffer week).** Personality, settings page, error handling, loading states, mobile layout. Catch up on anything that slipped.
- **Weekend 6 - Launch.** Demo video, final README, this SEEDFILE updated, LinkedIn and X post.

## Design rules

- Monochrome UI: black, white, greys. No color accents except status.
- Apple-inspired and lightweight: lots of space, simple type, small fast pages, no heavy libraries.
- Departure Mono is welcome for headings or labels (Nadeem uses it on his portfolio).
- Plain language everywhere: UI copy, README, code comments. Explain like to a smart mid-level developer.
- No feature without a visible demo. If you cannot show it in the UI, it is not done.
- Keep it small. Prefer one clear file over a clever abstraction.

## Working rules for AI assistants

- Nadeem is mid-level, not senior: explain new ideas in simple words, define jargon once.
- Do not paste secrets. API keys go in `.env.local` (git-ignored) and in Vercel project settings.
- Only change this repo. Keep commits small and named by what the user can see.
- Update the "Status" section below at the end of every working session.

## Status

Done:
- Weekend 0: fresh Next.js scaffold (App Router, TypeScript, ESLint), monochrome placeholder home page, README, this SEEDFILE.

Planned (not started):
- Everything in the weekend milestones above, starting with Weekend 1.

## Resume bullets this project earns (draft, edit with real numbers when done)

- Built and deployed a full-stack AI agent (Next.js, Vercel AI SDK, Postgres) with persistent memory and autonomous task execution through tool calling.
- Designed a tool-calling layer where the model decides when to save memories and create todos, with every action shown to the user as a live action card.
- Shipped to production on Vercel with a Neon Postgres backend; documented with a README and SEEDFILE so any AI or developer can continue the work.
