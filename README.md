# Minaam Ahmad

MERN developer. I ship the full thing — auth, real-time layer, and the deploy that breaks in ways tutorials don't cover.

[LinkedIn](https://linkedin.com/in/minaamahmad123) · [Portfolio](http://minaamahmad.me/) · [Medium](https://medium.com/@minaamahmad) · [minaamahmad@gmail.com](mailto:minaamahmad@gmail.com)

---

### What I'm building right now

A real-time multiplayer card game — the part everyone underestimates is the state sync, not the UI. Here's the shape of it:

```ts
// gameEngine.ts — every action returns a typed result, never a bare exception.
// The server broadcasts on success, replies with the reason on failure —
// no client ever guesses why a move was rejected.

type ActionResult<T> =
  | { ok: true; state: T }
  | { ok: false; reason: 'not_your_turn' | 'invalid_move' | 'room_full' };

function playCard(room: GameRoom, playerId: string, card: Card): ActionResult<GameState> {
  if (room.currentTurn !== playerId) return { ok: false, reason: 'not_your_turn' };
  if (!isLegalMove(room.state, card))  return { ok: false, reason: 'invalid_move' };

  const state = applyMove(room.state, card);
  return { ok: true, state };
}
```

Next.js 16 + React 19 on the client, Socket.IO for the room/turn logic, a React Native port so it isn't stuck in the browser. Repo: [github.com/Minaamahmad/game](https://github.com/Minaamahmad/game)

### Shipped, not just committed

**Prime Booking** — hotel booking platform, MERN + Socket.IO + Google OAuth + JWT/RBAC, live on Vercel/Render.
The interesting part wasn't the CRUD — it was getting cross-origin cookies (`sameSite: 'none'`, `secure: true`) and the OAuth redirect URIs to actually agree with each other in production.

**AutoBot** — a Node.js service that pulls TikTok videos and reposts them to Facebook Pages on a cron, backed by Redis, talking to the Graph API with a permanent Page token.
Migrated `yt-dlp` into Docker mid-project after Render's environment stopped cooperating with cookie-based auth.

**Capture Cards** — see above.

### Stack I reach for

`JavaScript` `TypeScript` `React` `Next.js` `Node.js` `Express` `Socket.IO` `MongoDB` `PostgreSQL` `Python` `Docker`

Currently adding FastAPI and Odoo to that list.

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=MinaamAhmad&show_icons=true&theme=transparent&title_color=58A6FF&text_color=c9d1d9&icon_color=58A6FF&hide_border=true&count_private=true" width="48%" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=MinaamAhmad&layout=compact&theme=transparent&title_color=58A6FF&text_color=c9d1d9&hide_border=true" width="42%" />
</p>
