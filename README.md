<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-dark.svg">
  <img src="assets/banner-light.svg" alt="Anuj Malviya — Full-stack engineer" width="100%">
</picture>

<br>

I build full-stack systems from primitives — and stay to fix what breaks in production.

Every project I've shipped has taught me the same lesson from a different angle: the happy path is the easy part. A peer-to-peer interview platform, a finance dashboard, a notes app on Redis-backed rate limiting, even a throwaway quote generator against an API that allows five requests an hour — each one turned out to be about failure states. Reconnection, cold starts, race conditions, 429s.

On MockHire I chose raw WebRTC over a paid SDK, then spent a week fixing offer collisions and ghost disconnects a managed service would have hidden. I'd make the same call again.

<br>

---

<br>

<p align="center">
  <img src="assets/mockhire-room.png" alt="MockHire interview room — peer video, chat, and shared code editor" width="49%">
  &nbsp;
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/p2p-dark.svg">
    <img src="assets/p2p-light.svg" alt="Architecture: encrypted media flows peer-to-peer; the server relays only SDP and ICE" width="33%">
  </picture>
</p>

<p align="center">
  <sub><b>MockHire</b> — peer-to-peer technical interviews.<br>
  Media never touches my server. No Twilio, no Agora, no SDK.</sub>
</p>

<p align="center">
  <a href="https://mockhire-1xn2.onrender.com"><img src="https://img.shields.io/badge/Live_demo-E8A94E?style=flat-square" alt="Live demo"></a>
  &nbsp;
  <a href="https://github.com/AnujMalviya2154/MockHire-Video-Interview-Platform"><img src="https://img.shields.io/badge/Source-30363D?style=flat-square" alt="Source"></a>
</p>

<br>

### Current focus

- **Building** — Production-grade full-stack applications with AI, real-time communication, and scalable architectures
- **Learning** — Cloud-native deployments, DevOps practices, scalable system design, and software architecture
- **Exploring** — Agentic AI systems, developer tooling, and building software that scales gracefully in production

<br>

---

<br>

### Featured work

#### 01 · MockHire

<sup>Self-hosted technical interview platform — P2P video, shared editor, structured feedback.</sup>

- Media bypasses the server entirely. It relays only SDP and ICE, which makes calls **physically un-recordable by design** rather than un-recorded by policy.
- Room codes are 128 bits from `crypto.randomBytes`, authorized server-side per socket against the DB, with an 8-hour expiry. A leaked URL still doesn't get you in.
- **52 integration tests** against a live server and a real database, covering IDOR, feedback privacy, socket authorization, and survival of a mid-flight DB outage.
- Binds its port *before* connecting to Mongo, then returns `503` + `Retry-After` until ready. Cold starts don't drop traffic.

<sup>React · Socket.IO · WebRTC · Express · MongoDB · Tailwind</sup>

<br>

#### 02 · Fintrak

<p align="left">
  <img src="assets/fintrak-dashboard.png" alt="Fintrak analytics dashboard" width="42%" align="right">
</p>

<sup>Personal finance dashboard — income and expense tracking with analytics and Excel export.</sup>

- Split deployment across Vercel and Render with CORS pinned to a single origin.
- Monthly overview and category-distribution charts, savings-rate computation, dark and light themes.

<sup>React 19 · Recharts · Express · MongoDB · JWT</sup>

<br clear="all">

<br>

<sub>Also here — <b>ThinkBoard</b>, a notes app with a Redis sliding-window limiter and a dedicated 429 state · <b>NeetCode-150</b>, ongoing DSA practice.</sub>

<br>

### How I work

> **Decisions get written down.**
> Every milestone in MockHire has a decision record in `docs/decisions/`. Six months from now I can still explain why the server binds before it connects — and, more usefully, what I'd have to believe to change it.

> **Bugs get instrumented, not guessed at.**
> Instrument, reproduce, fix, document, then remove the instrumentation. Three separate WebRTC failures went through that loop — including one I introduced while fixing the previous one. No diagnostic logging survived into `main`.

> **Security is a default, not a feature.**
> JWTs in httpOnly cookies rather than localStorage. Token-version revocation so logging out actually invalidates. Roles re-read from the database on every request instead of trusted from a payload the client holds.

> **Failure is the default case.**
> Servers boot before their database is reachable. Peers refresh mid-call. Free-tier APIs cut you off at five requests an hour. I design for those first and treat the happy path as the special case.

<br>

---

<br>

### Stack

- **Core** — React · Node · Express · MongoDB · Socket.IO
- **Real-time** — WebRTC · WebSockets · Redis
- **Also** — Tailwind · Bootstrap · C++

<br>

### Activity

<div class="stats-row">
  <img src="https://github-readme-stats.anuraghazra1.vercel.app/api?username=AnujMalviya2154&show_icons=true&include_all_commits=true&count_private=true&rank_icon=percentile&hide_border=true&bg_color=00000000&title_color=E8A94E&icon_color=E8A94E&text_color=768390" alt="GitHub stats" height="165">
  <img src="https://github-readme-streak-stats.herokuapp.com?user=AnujMalviya2154&hide_border=true&theme=transparent&ring=E8A94E&fire=E8A94E&currStreakLabel=E8A94E&sideLabels=768390&dates=768390&currStreakNum=768390&sideNums=768390&stroke=768390" alt="Contribution streak" height="165">
</div>

<div style="text-align:center; margin: 16px 0;">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=AnujMalviya2154&bg_color=00000000&color=768390&line=E8A94E&point=E8A94E&area_color=E8A94E&area=true&hide_border=true" alt="Contribution activity" width="98%">
</div>

<br>

---

<br>

### Contact

<p align="center">
  <a href="https://www.linkedin.com/in/anujmalviya764/" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/LinkedIn-30363D?style=flat-square" alt="LinkedIn"></a>
  &nbsp;
  <a href="mailto:anujmalviya76434@gmail.com" target="_blank" rel="noopener noreferrer"><img src="https://img.shields.io/badge/Email-30363D?style=flat-square" alt="Email"></a>
</p>

<p align="center">
  <sub>B.Tech CSE, VIT Bhopal · open to backend and full-stack roles</sub>
</p>

<br>

<p align="center">
  <sub><i>The bug you can't reproduce is the one you haven't instrumented yet.</i></sub>
</p>
