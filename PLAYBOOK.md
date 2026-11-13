# Playbook: using AI for mental health work, on your own terms

How to put together an AI setup for therapy-adjacent work (reflection, documentation,
preparing for appointments) where **the important parts belong to you**, not to one
company's chatbot. It is the companion to the tooling in this index: the tools are one way to
build it; this explains the moving parts so you can build it on any platform.

Adapted from a guide written for a friend on 2 November 2026. App features and prices were
checked on that date and change often; prices are in US dollars.

---

## The big idea: own the material, rent the AI

Most people open ChatGPT and rely on its built-in memory. That has its place, but it gives
unimpressive results for this kind of work, and everything you build lives inside one
product.

The alternative is an agentic scaffold you assemble yourself. Your life story, your notes and
the record of your sessions sit in **your own storage** (Google Drive, Dropbox, a git
repository). The AI app is just the thing you plug them into. If the app changes, gets worse or
drops a feature, you plug the same material into another one and carry on.

Lock-in is not theoretical. In late 2026 ChatGPT is retiring custom GPTs (they stop working on
11 December 2026) and Gemini is converting Gems into "Skills". Anyone whose setup lived only
inside those features has to rebuild it. If your material is in your own storage, you don't
care.

## Privacy: decide your own threshold first

Privacy thresholds differ, and the author's differs from many people's. This playbook uses
hosted services (cloud storage, cloud transcription, cloud models) because they are the easiest
route. If you want less to leave your machine, every part below has a local alternative: local
transcription, local storage, a desktop app, a local model. Decide where your line is before you
choose parts, not after.

---

## The parts

Three groups: **your material** is what you own, **the AI** is the swappable bit, and **how it
behaves** is how you set it up.

| Group | Part | What it does | Examples |
|---|---|---|---|
| Your material | **Personal context** | Your background: life history, family, the people who are good and bad for you, what you are working on. The AI reads it so you never explain yourself from scratch | Voice notes, transcribed |
| | **Transcription** | Turns voice notes into text the AI can read | AssemblyAI, Gemini, local tools |
| | **Your own storage** | The master copy of everything; goes with you from app to app | Google Drive, Dropbox, a private git repo |
| The AI | **The model** | The "brain" that does the talking. Swap brains without touching your material | Grok, GPT, Gemini, Claude, GLM |
| | **OpenRouter** | One account and key for hundreds of models, pay as you go, no subscriptions | openrouter.ai |
| How it behaves | **Knowledge** | Documents loaded into the AI that it can look things up in: your context. Fixed until you update it | Projects, uploaded files, AnythingLLM |
| | **Memory** | What the AI writes down as you talk, so it builds up session by session | Built-in memory, session notes, Mem0 |
| | **System prompt** | Standing instructions: who the AI is meant to be, what it is for, how to talk to you | The instructions box |
| | **Connectors (MCP)** | The AI's "hands": they let it do things, like save a file to your Drive after a session | Google Drive connector |

Knowledge and memory are different things. **Context** (knowledge) is the foundational
background, written once and updated as life changes. **Memory** is written as you go.

---

## Step 1: Collect your personal context

This is the foundation: your history, your background, the toxic people in your life.

It is hard to get this out of yourself by typing, so record **voice notes**, at length. Any
voice recorder on your phone will do. You only do this once in full, then update it as
circumstances change. Of all the steps, this is the one that matters most.

## Step 2: Transcribe

| Option | Notes |
|---|---|
| AssemblyAI | Very good; free credits on sign-up ($50 worth as of November 2026, which is many hours) |
| Gemini | Upload the recording and ask it to transcribe and lightly clean it up |
| Free / local | Plenty of transcription tools, including free ones that run on your own computer |

## Step 3: Keep it somewhere you own

Don't rely on built-in memory for something this important. Save the transcripts yourself, in
private storage you control. Then you can try different systems without ever recording again.

Suggested layout:

```
AI Context/     one document per topic: background, family, work, people, what I want to work on
Sessions/       where the AI saves its notes after each conversation
```

## Step 4: Pick a pathway

Same parts, different amounts of effort. All of them work with the folder from step 3.

| Pathway | What it looks like | Effort | Cost |
|---|---|---|---|
| **A. Grok** | A dedicated Grok bot with your context and a Drive connection | Easiest | Your Grok plan |
| **B. Another app** | The same idea in ChatGPT, Gemini or Claude | Easy | About $20/month |
| **C. DIY** | Your own app on your computer, any model via OpenRouter | An afternoon | Pennies per chat |
| **D. Agent platform** | A no-code automation tool wires the parts together | Some fiddling | Free tier, then paid |
| **E. Agent scaffold** | A coding agent working in a private repository, with skills for capture, mapping and documents | More setup, most capable | Agent subscription or API |

### A. Grok

1. Make a **dedicated bot** for this, separate from any others. Each Grok bot has its own
   conversation and memory, so this one stays private from the rest.
2. Give it your context: upload transcripts in the chat, or connect Google Drive
   (grok.com/connectors) so it can read your `AI Context/` folder directly.
3. Give it a system prompt (step 5).
4. Have it save notes to Drive: with the Drive connector on, ask it to end each session by
   saving a synopsis to `Sessions/`.

Grok's built-in memory is fine to leave on, but the Drive notes are the copy you own.

### B. ChatGPT, Gemini or Claude

| App | Where your context goes | Saving notes to Drive |
|---|---|---|
| ChatGPT | A Project: upload your files, choose project-only memory when you create it. Custom GPTs are being retired: don't start one | Google Drive connector |
| Gemini | Gems take files straight from Drive, but are being converted into "Skills" from November 2026 | Built in |
| Claude | A Project with your files as knowledge | Google Drive connector (paid plan) |

### C. DIY: the most sovereign version

1. **OpenRouter.** Load $10–20 and you need no subscriptions; you pay for what you use. Cheap
   models are plenty (GLM models, Gemini Flash); a long chat costs a few cents.
2. **AnythingLLM** (free, desktop). Paste in your OpenRouter key, create a workspace and drop
   your context documents in as knowledge. Everything lives on your computer.
3. **Connectors.** AnythingLLM supports MCP, which is how you add "save notes to Drive".
4. **Or build your own.** Any capable AI can help you write a simple chat interface that joins
   a model (through OpenRouter) to your files, in an afternoon.

### D. Agent platforms

No-code blocks you connect: "chat with this model, read this Drive folder, save a summary
there afterwards". More fiddly than A or B, very flexible.

| Platform | Free to start? |
|---|---|
| Zapier (Agents) | Free plan with a monthly allowance; paid from about $20/month |
| Make | Free plan with monthly credits |
| n8n | Cloud free trial, or free self-hosted; paid from about €20/month |

### E. Agent scaffold

The tooling in this index. A coding agent (Claude Code, or any agent that reads an
`AGENTS.md`) works in a private repository that holds your material, with skills that do the
heavy lifting: structured capture interviews, voice-note ingestion, a mapped family system,
session tracking, intake packs for a therapist. Start with the
[Personal-Context](https://github.com/danielrosehill/Claude-Personal-Context-Plugin) plugin for
background, add [Family-Systems-Context](https://github.com/danielrosehill/Family-Systems-Context-Plugin)
if the family is the tangle, and a
[therapy workspace](https://github.com/danielrosehill/Claude-Therapy-Workspace-Template) per
issue. The repositories are plain markdown, so the material stays portable to every other
pathway.

## Step 5: The system prompt

The system prompt defines the objectives: who the AI is meant to be and what a session looks
like. You might set it up as a reflection partner, or as a roleplay for a difficult
conversation. The most useful instruction is to **write things up afterwards**.

```text
You're my reflection partner. Read my context documents before replying,
so I don't have to repeat my background. Talk to me like a sharp, honest
friend, not a hotline. At the end of each session, write a synopsis of what
we discussed and a few practical tips, and save it as a PDF to my Google
Drive in Sessions/.
```

## Step 6: A memory layer (optional, later)

Knowledge is the fixed material from step 1. Memory is written as you go, so you stop repeating
yourself and the record builds up somewhere you control.

The session notes in `Sessions/` are already a simple memory you own. For a proper memory
layer, look at Mem0 for memory and a vector database (Pinecone, Qdrant) for storing your
knowledge yourself. They have free tiers but are aimed at builders, so they suit pathways C, D
and E rather than A or B.

---

## What this is, and isn't

None of this is therapy. It is a sidecar to it: a way to document, organise and prepare, so the
time with a professional goes on the real work, and the long gaps between appointments are not
wasted. If things are acute, contact a person: <https://findahelpline.com>.

Moving parts, but they are worth moving.
