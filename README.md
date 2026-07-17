<h1 align="center">Rajat Tripathi 👋</h1>

<p align="center">
  <b>Founder of <a href="https://siliconboard.co">SiliconBoard</a></b> &nbsp;·&nbsp; ex–Team Lead @ Xalts &nbsp;·&nbsp; 100% technical
</p>
<p align="center">
  <em>I build GenAI plumbing — MCP servers, scrapers, voice/video + LLM pipelines — and point it at boring, high-value workflows so the agent does the part nobody wants to do twice</em>
</p>

<p align="center">
  <a href="https://siliconboard.co"><img src="https://img.shields.io/badge/SiliconBoard-siliconboard.co-1A1A1A?style=for-the-badge&logo=googlechrome&logoColor=D6FD61" /></a>
  <a href="https://apps.tripathirajat.com"><img src="https://img.shields.io/badge/Portfolio-apps.tripathirajat.com-0A66C2?style=for-the-badge" /></a>
  <a href="mailto:triprjt@gmail.com"><img src="https://img.shields.io/badge/Email-triprjt@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/triprjt"><img src="https://img.shields.io/github/followers/triprjt?label=Follow&style=for-the-badge&logo=github" /></a>
</p>

---

## 🟢 SiliconBoard — the flagship

**[siliconboard.co](https://siliconboard.co)** — the job board built for semiconductor careers in India. Live job scrapers → a normalized role &amp; skill taxonomy → salary benchmarking → **LLM-generated job-readiness reports**. I own the whole stack end to end:

- **Backend** — Node / Express API, libSQL / SQLite, background scrapers
- **Frontend** — Astro SSR + a vanilla-JS candidate dashboard
- **Data / AI** — role→skill indexing, salary estimation, a resume→report LLM pipeline
- **Infra** — nginx, PM2, DigitalOcean, Playwright E2E

---

## 🧭 The thesis

LLMs are a commodity. The **plumbing around them** — MCP servers, agent harnesses, scrapers, idempotent deploy systems — is where the leverage sits. I build the plumbing, then point it at high-value workflows (semiconductor hiring, D2C marketing, founder content) so the agent does the boring part.

Right now: **MCP-first development**, **personalised video at scale** (lip-sync + voice clone at ₹2–5/video), **Indic GenAI** (Hindi / Tamil / Telugu voice + avatar), and **autonomous content loops** (Exa → Claude → Veo → Cartesia → FFmpeg → social).

---

## 🚀 Featured systems

### [🎯 SiliconBoard](https://siliconboard.co)
Semiconductor job board + LLM job-readiness reports (see above). Node · Astro SSR · libSQL / SQLite · resume→report LLM pipeline · Playwright E2E.

### [🎙️ FolkTalk-MCP](https://github.com/triprjt/folktalk-mcp) *(in progress)*
MCP server wrapping a self-hosted lip-sync stack (MuseTalk + Cartesia voice clone + Veo 3.1 b-roll), exposing 7 tools from `clone_voice` to `generate_batch`. Turns "thank every paying customer by name" into a Claude one-liner. Unit economics: ~$0.03 per 30s personalised video, ~75% gross margin at ₹3/video.

### [📧 Kit-MCP — email automation](https://github.com/triprjt/convertikit-deploy) *(in progress)*
Idempotent deployment pipeline that takes a markdown spec (5 forms, 55 tags, 14 sequences, 40+ emails) and pushes it to ConvertKit V4 via API — the 3–5 days of clicking the docs estimate, done in one `npm run deploy`.

### [🔎 ViralFinder](https://apps.tripathirajat.com)
Live app that surfaces breakout consumer-app trends from social signal data so indie devs ship the right thing this week, not next quarter. Public at `apps.tripathirajat.com`.

### [📂 fileSyncing — DaVinci → DO Spaces](https://github.com/triprjt/fileSyncing)
Event-driven (not polling) macOS launchd service: fswatch detects a new export → size-stability wait → ffmpeg H.265 (CRF 28, libx265 + hvc1) → rclone push to DigitalOcean Spaces → local delete on exit 0. Zero polling, zero wasted disk.

### [🧬 emailVectorDB](https://github.com/triprjt/emailVectorDB) · [🔍 viralapphunter](https://github.com/triprjt/viralapphunter)
Semantic search over an email corpus (the substrate behind the personalisation work); and a scorer for newly-launched consumer apps that feeds ViralFinder.

---

## 🛠️ Stack I actually ship with

```
Product        SiliconBoard (semiconductor job board + LLM reports) · ViralFinder
LLMs           Claude (Opus 4.8, Sonnet 4.6) · GPT-4o · Gemini 2.5
Agent runtime  Claude Agent SDK · MCP (Python FastMCP + TS SDK) · LangGraph
Video          Veo 3.1 · Kling 3.0 · Wan 2.6 · MuseTalk · LatentSync
Voice          Cartesia Sonic · ElevenLabs · F5-TTS · Indic-Parler-TTS
Vector / RAG   pgvector · Qdrant · Turbopuffer
Backend        Node 20 · TypeScript · FastAPI · Astro · Postgres (Supabase) · libSQL / SQLite · Cloudflare R2
Infra          Modal (A100/H100) · DigitalOcean · Vercel · nginx · PM2 · Playwright
Frontend       Next.js 15 · Astro · Tailwind · shadcn/ui
```

---

## 📐 Principles I keep coming back to

1. **Idempotency is non-negotiable** — every deploy script does `GET → if exists skip → else POST → persist ID before the next call`. Re-running a script is the only acceptable recovery mode.
2. **Expose every system as an MCP tool.** If Claude can drive it from chat, the system is 10× more reusable than a CLI wrapper.
3. **State files > a database for solo projects.** Atomic write-to-tmp-then-rename + a `state.json` source of truth beats spinning up Postgres for the 99% of single-user agentic scripts.
4. **Self-host the GPU layer past ~10k inferences/month.** MuseTalk on Modal A100 at $0.03/video crushes any API once volume kicks in — and provider arbitrage is real (same weights, 3.75× price gaps).

---

## 📊 GitHub

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=triprjt&show_icons=true&theme=tokyonight&hide_border=true&count_private=true&include_all_commits=true" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=triprjt&layout=compact&theme=tokyonight&hide_border=true&langs_count=8" />
</p>

---

## 🤝 Open to

- MCP server / Claude Agent SDK contract work
- D2C / EdTech founders who want personalised-video automation wired into Razorpay / Shopify / WhatsApp Business
- Indic-language voice &amp; video pipeline collabs
- Anyone building agentic content loops at scale

**Reach me:** [triprjt@gmail.com](mailto:triprjt@gmail.com) · [siliconboard.co](https://siliconboard.co) · [apps.tripathirajat.com](https://apps.tripathirajat.com)
