# Mental Health AI Index

[![Master Index](https://img.shields.io/badge/Master_Index-GitHub-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Start-Here)

[![Index Repo](https://img.shields.io/badge/Type-Index_Repo-purple?style=flat-square)](https://github.com/danielrosehill/Subindices)

[![License](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)

AI tools, on any platform, for **mental health work that a person does on their own material**:
documenting what happened, mapping a difficult family, tracking a course of therapy, preparing for
an appointment, and keeping the background context that makes any of it repeatable. Plus the
policy work on access to care, and the ideas still being worked out.

Formerly `Claude-Mental-Health-Templates-Index` (renamed 2026-11-13 when it widened beyond
Claude Code; the old URL redirects).

**Last Updated:** November 2026

---

## Why these exist

The public debate about AI and mental health is mostly about whether a chatbot should be your
therapist. That question misses most of what AI is actually good for here.

People who come out of abusive or chaotic family systems are often, understandably, confused by
them: many people, shifting alliances, things that only make sense as a pattern over years. A
great deal of useful work sits well short of therapy:

- **Documenting** what happened, accurately and with dates, so a professional can read it.
- **Staying organised**: one place for the background, the incidents, the notes from each session.
- **Preparing** for appointments, so the professional hour goes on the real work instead of
  reconstruction.
- **Basic analysis**: understanding how a toxic person or system behaves. This does cross into the
  therapeutic, because understanding is therapeutic, but it is analysis of material, not treatment.

None of this replaces a therapist. It is a sidecar to one: it makes the professional time count,
and it fills the long gaps between appointments that access to care leaves. See
[SCOPE.md](SCOPE.md) for where the line is drawn.

**New to this? Start with the [Playbook](PLAYBOOK.md):** the moving parts of an AI setup for
this kind of work (context, transcription, your own storage, model, knowledge, memory, system
prompt, connectors), how to avoid platform lock-in, and five pathways from a Grok bot to a full
agent scaffold.

---

## Practical tooling

### Claude Code plugins

Installable from the [danielrosehill marketplace](https://github.com/danielrosehill/Claude-Code-Plugins).
Add it once:

```bash
/plugin marketplace add danielrosehill/Claude-Code-Plugins
```

| Plugin | What it does | Install | Links |
|--------|--------------|---------|-------|
| **Family-Systems-Context** | Maps a toxic or abusive family system as persistent context: one linked file per person, roles and dynamics described through family-systems research (Bowen, Minuchin, genograms, parentification, DARVO) with evidence tiers, a glossary mapping the informal abuse-recovery vocabulary ("flying monkeys", "hoovering", "golden child") to research constructs, a printable relationship diagram, a therapy intake-pack PDF, voice-note capture, aliases for names that are hard to see, and an optional vector-store mirror. The user's account is the record; it describes, it doesn't diagnose | `/plugin install family-systems-context@danielrosehill` | [![Repo](https://img.shields.io/badge/View-Repo-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Family-Systems-Context-Plugin) [![Claude Code](https://img.shields.io/badge/Claude_Code-Marketplace-D97757?style=flat-square&logo=anthropic)](https://github.com/danielrosehill/Claude-Code-Plugins) |
| **Personal-Context** | Builds and maintains a persistent background context layer: intake interview, ingestion of material you already have (journals, exports, old notes), gap analysis, scoped retrieval, maintenance and export. Ships the **Portable Context Contract**: plain markdown in a store you own; model-managed memory is ruled out by the spec | `/plugin install personal-context@danielrosehill` | [![Repo](https://img.shields.io/badge/View-Repo-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Personal-Context-Plugin) [![Claude Code](https://img.shields.io/badge/Claude_Code-Marketplace-D97757?style=flat-square&logo=anthropic)](https://github.com/danielrosehill/Claude-Code-Plugins) |
| **Therapy-Tracking** | Pre- and post-session notes, goal tracking, and turning voice-memo transcripts into structured problem summaries, across an ongoing course of therapy. Data lives outside the plugin; git mode defaults to local-only | `/plugin install therapy-tracking@danielrosehill` | [![Repo](https://img.shields.io/badge/View-Repo-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Therapy-Tracking-Plugin) [![Claude Code](https://img.shields.io/badge/Claude_Code-Marketplace-D97757?style=flat-square&logo=anthropic)](https://github.com/danielrosehill/Claude-Code-Plugins) |
| **Personal-Planning** | General personal-planning workspaces: `log-entry` / `set-goal` / `review-progress` across diary, health-wellness, personal-dev and therapy variants. The broad tool the two above specialise | `/plugin install personal-planning@danielrosehill` | [![Repo](https://img.shields.io/badge/View-Repo-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Personal-Planning-Plugin) [![Claude Code](https://img.shields.io/badge/Claude_Code-Marketplace-D97757?style=flat-square&logo=anthropic)](https://github.com/danielrosehill/Claude-Code-Plugins) |

### Workspace templates

GitHub templates: create a **private** repository from one and open it with an agent. Plain
markdown with their own agent instructions, so they run without any plugin installed.

| Template | What it is for | Links |
|----------|----------------|-------|
| **Claude-Therapy-Workspace-Template** | Working through **one bounded issue** (a career situation, one relationship, a bereavement). One workspace, one issue, with an ending. Skills to capture a session, unpack an incident, build a chronology from raw material, re-read it through other lenses, review what recurs, draft the hard message, and produce a two-page handover for an appointment | [![Use template](https://img.shields.io/badge/Use-Template-green?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-Therapy-Workspace-Template/generate) |
| **Family-System-Context-Template** | The private family-data workspace behind Family-Systems-Context. Its `AGENTS.md`, docs and procedures are agent-agnostic, so a ChatGPT agent or a Grok bot can follow them | [![Use template](https://img.shields.io/badge/Use-Template-green?style=flat-square&logo=github)](https://github.com/danielrosehill/Family-System-Context-Template/generate) |

### Assistant configurations (any platform)

System prompts to set up as assistants in whichever chat frontend you use.

| Project | Description | Links |
|---------|-------------|-------|
| **Narcissistic-Abuse-Support-Configs** | A network of assistant configurations for people affected by relationships with personality-disordered individuals, in eleven groups: documentation (therapy prep and take-home notes), education, ethics, family navigation, harm mitigation (boundaries, safety planning), identification (gaslighting and manipulation spotting), recovery, roleplay practice, strategy and support, plus an orchestrator. Each file is a ready system prompt with implementation notes; framed as an adjunct to professional care | [![View Dataset](https://img.shields.io/badge/View-Dataset-yellow?style=flat-square&logo=huggingface)](https://huggingface.co/datasets/danielrosehill/Narcissistic-Abuse-Support-Configs) |

---

## Adapting to other platforms

Everything above was built in Claude Code or as plain system prompts, but none of it depends on
one vendor. The same patterns adapt to ChatGPT agents and custom GPTs, Grok bots, Open WebUI,
or anything else that takes instructions and files. A mental-health agent on any platform rests
on the same foundations:

| Foundation | What it is | How it shows up here |
|------------|------------|----------------------|
| **Memory** | What the agent retains between conversations: decisions, recent events, what was said last time | Kept in files you own (session notes, history logs), not in the platform's built-in memory, which can't be exported or scoped |
| **Context** | The foundational background: who you are, your history, the people involved. Distinct from memory: written once, read by everything | Personal-Context's store; Family-Systems-Context's family map |
| **Tool connections** | Access to where your material lives: Google Drive above all, plus mail and calendars | Drive or a git repository as the store; the agent reads and writes there |
| **Workloads** | The jobs themselves | Recording (voice notes in, transcribed and filed), documenting, analysis of patterns, preparing intake material |

The [Playbook](PLAYBOOK.md) walks through this step by step. In short: load the template's agent instructions as the system prompt or project instructions,
put the store in Drive or a connected repository, and give the agent the tool connections it
needs. Voice capture works anywhere: record a long voice note, transcribe it, and file the
transcript as source material.

---

## Health access and policy

Mental health work also runs into the system that is supposed to deliver care. These projects
document that system and work on policy for it. Also listed in the
[AI-Assisted-Policymaking-Index](https://github.com/danielrosehill/AI-Assisted-Policymaking-Index).

| Project | Description | Links |
|---------|-------------|-------|
| **Claude-ADHD-Research-Workspace** | A live, public research workspace on ADHD drug-access policy, run like a small think tank in a repository: context gathered and chunked, prompts staged and run, outputs distilled towards a position paper, with a lobbying stage that separates first drafts from authoritative policy proposals | [![Repo](https://img.shields.io/badge/View-Repo-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Claude-ADHD-Research-Workspace) |
| **Israel-ADHD-Medication-Access** | The evidence layer under that workspace: a redacted case record of trying to fill a valid ADHD prescription in Israel, from primary material (recordings, correspondence, closure letters). The published rules, the referral loop, and the regulation nobody mentioned | [![Repo](https://img.shields.io/badge/View-Repo-blue?style=flat-square&logo=github)](https://github.com/danielrosehill/Israel-ADHD-Medication-Access) |

---

## Ideation and experiments

Ideas being worked on, not yet published as tooling.

| Idea | Status | Description |
|------|--------|-------------|
| **Go-between agent** | Work in progress, not public | A sandboxed, intermediate space in which an agent acts as a go-between for a person and people whose contact is unwanted or hurtful, so the person does not have to deal with them directly |

---

## How they fit together

```text
  Personal-Context            ← who you are. Written once, read by everything.
  Family-Systems-Context      ← the family you came from, mapped and kept current.
                    │  scoped reads
     ┌──────────────┼──────────────┐
     ▼              ▼              ▼
  therapy        therapy        a ChatGPT agent,
  workspace      workspace      a Grok bot, any
  (issue A)      (issue B)      other assistant
     │
     ▼
  for-therapist/ + intake pack ─────────►  a real appointment
                                                 │
                                                 ▼
                                       Therapy-Tracking
                                       (the ongoing course, tracked)
```

Choosing between them:

- **Working on one thing?** → therapy workspace template. Bounded, closeable, produces documents.
- **Is the family itself the tangle?** → Family-Systems-Context: map it once, keep it current,
  hand the diagram and intake pack to a therapist.
- **In therapy and want the sessions tracked?** → Therapy-Tracking.
- **Tired of re-explaining yourself?** → Personal-Context. Everything else reads it.
- **Not on Claude Code?** → the assistant configurations, or adapt a template (above).

## Common thread

| | |
|---|---|
| **Organising, documenting, preparing** | The value is mostly in the unglamorous work: a clear record, a chronology, a brief a professional can read in five minutes |
| **The user is believed** | The person's account is the record. Tools describe what happened and map it; they don't cross-examine it |
| **Portable context, not vendor memory** | Background context is plain files in a store the person owns, read through declared scopes. Model-managed memory can't be exported, can't be scoped, and dies with the account |
| **Documents are the output** | The conversation is the means. What survives is a session note, a chronology, a diagram, an intake pack: reviewable later and usable by a professional |
| **The bridge, not the destination** | Access to support is rationed by cost, waiting lists, geography and language. Organised material is useful on its own *and* makes the professional hour better |
| **Private by default** | Personal material never goes near a public remote |
| **Describe, don't diagnose** | No screening scores, no diagnoses of anyone. Research concepts are used to name patterns, with their evidence level stated |

## License

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
