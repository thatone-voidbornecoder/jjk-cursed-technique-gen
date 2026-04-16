# Cursed Technique Generator

An AI-powered Jujutsu Kaisen themed sorcerer profile generator. Adjust personality sliders, pick a mentor, enable special modes, and receive a fully fleshed-out JJK-authentic cursed technique profile powered by GPT-5.2.

## Features

- **Personality-driven generation** — Calm/Chaotic, Logical/Emotional, Introverted/Extroverted, Strategic/Impulsive sliders shape your entire technique
- **Mentor influence** — Gojo Satoru, Nanami Kento, Yaga Masamichi, Haibara Yu, Suguru Geto, Mei Mei each leave their mark on the naming and style
- **Vibe Mode** — wildly exaggerated, chaotic manifestations
- **Cursed Weapon Wielder** — generates an original cursed tool alongside your technique (name, type, grade, ability, lore)
- **Heavenly Restriction** — sacrifice all cursed energy for physical perfection (Toji/Maki path)
- **Full profile output**: cursed energy type, innate technique, 3 extension techniques, domain expansion, binding vow, technique weakness, reverse cursed technique compatibility, sorcerer grade, clan affiliation, Tengen narration
- **Technique Clash** — pit two technique profiles against each other for a lore-accurate Tengen-narrated outcome
- **Session history** — up to 10 techniques saved in localStorage, survives page refresh
- **Share Link** — encode any technique in a URL to share with anyone
- **Copy Profile** — copy formatted technique text to clipboard
- **Export Image** — save the technique card as a PNG

## Project Structure

```
artifacts/
  api-server/          Express backend — AI generation routes
  cursed-technique-generator/  React + Vite frontend
lib/
  api-spec/            OpenAPI spec
  api-zod/             Generated Zod validation types
```

## Running locally

Requires Node.js 18+ and pnpm.

```bash
pnpm install
pnpm --filter @workspace/api-server run dev      # starts backend on PORT
pnpm --filter @workspace/cursed-technique-generator run dev  # starts frontend
```

Set the following environment variables for the backend:

```
AI_INTEGRATIONS_OPENAI_BASE_URL=<your openai-compatible base url>
AI_INTEGRATIONS_OPENAI_API_KEY=<your api key>
SESSION_SECRET=<any random string>
DATABASE_URL=<postgres connection string>
```

The app uses `gpt-5.2` by default. Change the model in `artifacts/api-server/src/routes/cursed/index.ts` if needed.
