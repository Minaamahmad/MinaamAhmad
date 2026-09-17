<div align="center">

<img src="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=500&size=22&duration=2800&pause=900&color=58A6FF&center=true&vCenter=true&width=760&height=55&lines=I+build+systems%2C+not+just+interfaces.;MERN+%2B+TypeScript+%2B+Realtime;Shipping+is+part+of+the+engineering." alt="Typing introduction" />

<br>

```text
┌──────────────────────────────────────────────────────────────┐
│  MINAAM AHMAD                                                │
│  ────────────────────────────────────────────────────────────  │
│  MERN DEVELOPER  /  REALTIME  /  BACKEND  /  DEPLOYMENT      │
└──────────────────────────────────────────────────────────────┘
```

[![Portfolio](https://img.shields.io/badge/PORTFOLIO-0A0A0A?style=for-the-badge\&logo=vercel\&logoColor=58A6FF)](http://minaamahmad.me/)
[![LinkedIn](https://img.shields.io/badge/LINKEDIN-0A0A0A?style=for-the-badge\&logo=linkedin\&logoColor=58A6FF)](https://linkedin.com/in/minaamahmad123)
[![Medium](https://img.shields.io/badge/MEDIUM-0A0A0A?style=for-the-badge\&logo=medium\&logoColor=58A6FF)](https://medium.com/@minaamahmad)

</div>

---

```text
$ whoami

minaam-ahmad
```

I'm a **MERN developer** interested in the parts of software that become
interesting when more than one thing is happening at once.

```text
AUTH ────────────┐
REALTIME ────────┤
BACKEND ─────────┼──────►  PRODUCT
DATABASE ────────┤
DEPLOYMENT ──────┘
```

I like building things where the difficult part isn't making the button work.

It's making sure the button still works when:

* two users click it at the same time
* authentication crosses domains
* state changes in real time
* the database is involved
* the environment changes from localhost to production
* the deployment decides to become interesting

---

# `01` / CURRENT BUILD

### CAPTURE CARDS

**A real-time multiplayer card game.**

The UI is only one layer.

The actual problem is **state synchronization**.

The server owns the game state.
Clients request actions.
The server validates them.
Successful actions are broadcast.
Rejected actions return an explicit reason.

```ts
type ActionResult<T> =
  | {
      ok: true;
      state: T;
    }
  | {
      ok: false;
      reason:
        | "not_your_turn"
        | "invalid_move"
        | "room_full";
    };

function playCard(
  room: GameRoom,
  playerId: string,
  card: Card
): ActionResult<GameState> {

  if (room.currentTurn !== playerId)
    return {
      ok: false,
      reason: "not_your_turn"
    };

  if (!isLegalMove(room.state, card))
    return {
      ok: false,
      reason: "invalid_move"
    };

  const state = applyMove(room.state, card);

  return {
    ok: true,
    state
  };
}
```

**Client**

`Next.js 16` · `React 19`

**Realtime**

`Socket.IO`

**Mobile**

`React Native`

**Architecture**

`server-authoritative state`

→ **[github.com/Minaamahmad/game](https://github.com/Minaamahmad/game)**

---

# `02` / SHIPPED

## PRIME BOOKING

Hotel booking platform.

```text
MERN
├── Google OAuth
├── JWT
├── RBAC
├── Socket.IO
└── Vercel + Render
```

The CRUD wasn't the interesting part.

Production authentication was.

Getting these pieces to agree:

```text
browser
   │
   ▼
frontend origin
   │
   ├──── cookies
   │
   ├──── sameSite
   │
   ├──── secure
   │
   └──── OAuth redirect
             │
             ▼
          backend
```

was a much better engineering lesson than another CRUD tutorial.

---

## AUTOBOT

A Node.js automation service for scheduled TikTok → Facebook Page publishing.

```text
             ┌───────────┐
             │  TikTok   │
             └─────┬─────┘
                   │
                   ▼
              yt-dlp
                   │
                   ▼
              Node.js
                   │
             ┌─────┴─────┐
             │   Redis   │
             └─────┬─────┘
                   │
                   ▼
          Facebook Graph API
                   │
                   ▼
             Facebook Page
```

When the deployment environment stopped cooperating with
cookie-based authentication:

**the solution was Docker.**

Not a new tutorial.

Not a new stack.

Just another production problem.

---

# `03` / ENGINEERING INTERESTS

```text
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  REALTIME                                               │
│  ├─ WebSockets                                          │
│  ├─ state synchronization                               │
│  └─ server-authoritative systems                        │
│                                                         │
│  BACKEND                                                │
│  ├─ REST APIs                                           │
│  ├─ authentication                                      │
│  ├─ RBAC                                                │
│  └─ background jobs                                     │
│                                                         │
│  INFRASTRUCTURE                                         │
│  ├─ Docker                                              │
│  ├─ deployment                                          │
│  └─ production debugging                                │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

I'm particularly interested in the transition from:

```text
"it works"
      ↓
"it works reliably"
      ↓
"it works for multiple users"
      ↓
"it works in production"
```

---

# `04` / STACK

<div align="center">

### LANGUAGES

<img src="https://skillicons.dev/icons?i=js,ts,py&theme=dark" alt="Languages" />

### FRONTEND

<img src="https://skillicons.dev/icons?i=react,nextjs,html,css&theme=dark" alt="Frontend" />

### BACKEND

<img src="https://skillicons.dev/icons?i=nodejs,express,fastapi&theme=dark" alt="Backend" />

### DATA / INFRA

<img src="https://skillicons.dev/icons?i=mongodb,postgres,redis,docker&theme=dark" alt="Database and infrastructure" />

### TOOLS

<img src="https://skillicons.dev/icons?i=git,github,vscode,postman,vercel&theme=dark" alt="Tools" />

</div>

---

# `05` / NOW

```text
CURRENT

[██████████████████░░]  realtime systems
[███████████████░░░░░]  TypeScript
[████████████░░░░░░░░]  backend architecture
[███████████░░░░░░░░░]  FastAPI
[████████░░░░░░░░░░░░]  Odoo
```

Not a percentage of mastery.

Just a snapshot of what I'm spending time on.

---

# `06` / GITHUB SIGNAL

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=MinaamAhmad&show_icons=true&hide_border=true&bg_color=0A0A0A&title_color=58A6FF&text_color=EDEDED&icon_color=58A6FF&include_all_commits=true" width="49%" alt="GitHub statistics" />

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=MinaamAhmad&layout=compact&hide_border=true&bg_color=0A0A0A&title_color=58A6FF&text_color=EDEDED&langs_count=8" width="40%" alt="Top languages" />

</div>

<br>

<div align="center">

<img src="https://github-readme-streak-stats.herokuapp.com/?user=MinaamAhmad&theme=dark&hide_border=true&background=0A0A0A&ring=58A6FF&fire=58A6FF&currStreakLabel=58A6FF" width="70%" alt="GitHub streak" />

</div>

---

# `07` / CONTRIBUTION MAP

<div align="center">

<img src="https://ghchart.rshah.org/58A6FF/MinaamAhmad" alt="Minaam Ahmad's GitHub contribution graph" />

</div>

---

# `08` / OUTSIDE THE CODE

I write about things I actually run into while building.

Not:

> "10 React tips every developer needs."

More like:

> "Why did this authentication cookie disappear in production?"

The goal is simple:

**build → break → understand → document → build again**

---

# `09` / CONTACT

<div align="center">

### If you're building something difficult, I'm interested.

<br>

[![Email](https://img.shields.io/badge/EMAIL-minaamahmad%40gmail.com-0A0A0A?style=for-the-badge\&logo=gmail\&logoColor=58A6FF)](mailto:minaamahmad@gmail.com)

<br><br>

[Portfolio](http://minaamahmad.me/) ·
[LinkedIn](https://linkedin.com/in/minaamahmad123) ·
[Medium](https://medium.com/@minaamahmad) ·
[GitHub](https://github.com/Minaamahmad)

<br><br>

<sub>build things that survive localhost.</sub>

</div>
