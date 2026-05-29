<h1 align="center">Rajat Tripathi</h1>
<p align="center">
  <em>Shipping GenAI systems where the agent does the boring part — MCP servers, voice/video pipelines, autonomous reels.</em>
</p>

<p align="center">
  <a href="https://apps.tripathirajat.com"><img src="https://img.shields.io/badge/Live-apps.tripathirajat.com-0A66C2?style=for-the-badge" /></a>
  <a href="mailto:triprjt@gmail.com"><img src="https://img.shields.io/badge/Email-triprjt@gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://github.com/triprjt"><img src="https://img.shields.io/github/followers/triprjt?label=Follow&style=for-the-badge&logo=github" /></a>
</p>

---

## 🧭 The thesis

LLMs are a commodity. The **plumbing around them** — MCP servers, voice/video pipelines, agent harnesses, idempotent deploy systems — is where actual leverage sits. I build the plumbing, then point it at boring high-value workflows (D2C marketing, EdTech sequences, founder content) so the agent does the part nobody wants to do twice.

Focus areas right now:

- **MCP-first development** — every system I build exposes an MCP surface so Claude / Codex / Cursor can drive it
- **Personalised video at scale** — lip-sync + voice clone pipelines for D2C founders priced at ₹2–5/video instead of $30/video
- **Indic GenAI** — Hindi / Tamil / Telugu voice + avatar pipelines (Cartesia, F5-TTS, Indic-Parler, XTTS v2)
- **Autonomous content loops** — Exa → Claude → Veo → Cartesia → FFmpeg → social, running while I sleep

---

## 🛠️ Stack I actually ship with

```
LLMs           Claude (Opus 4.7, Sonnet 4.6) · GPT-4o · Gemini 2.5
Agent runtime  Claude Agent SDK · MCP (Python FastMCP + TS SDK) · LangGraph
Video          Veo 3.1 Lite · Kling 3.0 · Wan 2.6 · MuseTalk · LatentSync
Voice          Cartesia Sonic · ElevenLabs · F5-TTS · Indic-Parler-TTS
Vector / RAG   pgvector · Qdrant · Turbopuffer
Backend        Node 20 · TypeScript · FastAPI · Postgres (Supabase) · Cloudflare R2
Infra          Modal (A100/H100) · DigitalOcean Spaces · Vercel · Railway
Frontend       Next.js 15 · Astro · Tailwind · shadcn/ui
```

---

## 🚀 Featured systems

### [🎯 ViralFinder](https://apps.tripathirajat.com)
Live app that surfaces breakout consumer-app trends from social signal data so indie devs can ship the right thing this week, not next quarter. Public at `apps.tripathirajat.com`.

### [🎙️ FolkTalk-MCP](https://github.com/triprjt/folktalk-mcp) *(in progress)*
MCP server that wraps a self-hosted lip-sync stack (MuseTalk + Cartesia voice clone + Veo 3.1 b-roll) and exposes 7 tools: `upload_base_video`, `clone_voice`, `generate_personalized_video`, `generate_batch`, `get_job_status`, `list_voices`, `list_base_videos`. Turns "thank every paying customer by name" into a Claude one-liner. Unit economics: ~$0.03 per 30s personalised video, ~75% gross margin at ₹3/video.

### [📧 Kit-MCP — GIICT email automation](https://github.com/triprjt/convertikit-deploy) *(in progress)*
Idempotent deployment pipeline that takes a markdown spec (5 forms, 55 tags, 14 sequences, 40+ emails) and pushes it to ConvertKit V4 via API — what the docs estimate as 3–5 days of clicking, done in one `npm run deploy`. Generates a residual `MANUAL_STEPS.md` for the bits the API doesn't cover (Visual Automations + DKIM).

### [📂 fileSyncing — DaVinci → DO Spaces auto-pipeline](https://github.com/triprjt/fileSyncing)
Event-driven (not polling) macOS launchd service: fswatch detects a new DaVinci export → bash worker waits for file-size stability → ffmpeg H.265 compression (CRF 28, libx265 + hvc1 tag) → rclone push to DigitalOcean Spaces → local delete on exit code 0. Zero polling, zero wasted disk. Public.

### [🧬 emailVectorDB](https://github.com/triprjt/emailVectorDB)
Vector-DB hello-world that ingests an email corpus, embeds it, and exposes semantic search — the substrate behind the rest of the personalisation work. Public.

### [🔍 viralapphunter](https://github.com/triprjt/viralapphunter)
Scrapes + scores newly-launched consumer apps for breakout potential. Feeds ViralFinder. Public.

---

## 📐 Design principles I keep coming back to

1. **State files > database for solo projects.** Atomic write-to-tmp-then-rename + a `state.json` source of truth beats spinning up Postgres for the 99% of single-user agentic scripts I write.
2. **Idempotency is non-negotiable** — every deploy script does `GET → if exists skip → else POST → persist ID before next call`. Re-running a script is the only acceptable recovery mode.
3. **Expose every system as an MCP tool.** If Claude can drive it from chat, the system is 10× more reusable than a CLI wrapper.
4. **Self-host the GPU layer when you'll do >10k inferences/month.** MuseTalk on Modal A100 at $0.03/video crushes any API once volume kicks in.
5. **Provider arbitrage matters.** Same Hunyuan weights cost 3.75× more on FAL than on WaveSpeed. Always compare.

---

## 📊 GitHub

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=triprjt&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=triprjt&layout=compact&theme=tokyonight&hide_border=true" />
</p>

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=triprjt&theme=tokyonight&hide_border=true" />
</p>

---

## 🤝 Open to

- MCP server / Claude Agent SDK contract work
- D2C / EdTech founders who want personalised-video automation wired into Razorpay / Shopify / WhatsApp Business
- Indic-language voice & video pipeline collabs
- Anyone building agentic content loops at scale

**Reach me:** [triprjt@gmail.com](mailto:triprjt@gmail.com) · [apps.tripathirajat.com](https://apps.tripathirajat.com)
