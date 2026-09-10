# Projects

Selected work across media processing, publishing platforms, applied AI, and developer tooling.

My professional projects are internal to LinkedIn. The descriptions below focus on the problems, architecture, operating model, and outcomes without exposing source code or private implementation details.

## Portfolio Focus

- **Media systems:** Ingest, transcoding, captions, quality analysis, document generation, and archiving
- **Publishing platforms:** Python services, REST APIs, validation, queues, and operator-facing tools
- **Applied AI:** Generation harnesses, evaluation, semantic matching, and human review
- **Platform leadership:** Cross-region adoption, operating standards, production readiness, and knowledge transfer

## Career Context

- **Staff Publication Workflow Engineer, LinkedIn** — April 2025–present
- **Senior Workflow Engineer, LinkedIn** — March 2021–April 2025
- Earlier LinkedIn roles: Workflow Engineer, Senior Compressionist, and Video Compressionist

## Professional Systems

### Pacman Publishing Orchestrator

**Role:** System owner and lead developer  
**Scope:** North American and European LinkedIn Learning publishing workflows  
**Stack:** Python, FastAPI, SQLite, Telestream Vantage, Linux

Publishing work previously depended on operators locating content, checking filenames and metadata, and submitting jobs manually. I designed Pacman to turn that process into a staged service:

1. Discover content ready for publishing
2. Apply locale, licensing, priority, and editorial-state rules
3. Validate the media package
4. Schedule work
5. Submit approved jobs to Telestream Vantage

The implementation uses reusable filters and source/destination adapters so regional workflow changes do not require separate pipelines. I later added self-service APIs, preflight validation, retry windows, failure summaries, editorial escalation, and health alerts.

No-touch ingest increased from 55.6% in September to 100% in December 2025 across 455 reported ingests. The service remains active in production.

### Microsoft Whisper Captioning in Telestream Vantage

**Role:** Publishing Operations integration owner  
**Scope:** Requirements, UAT, release sign-off, regression testing, and post-launch support  
**Stack:** Microsoft Whisper, Telestream Vantage, Python, SRT caption workflows

I worked with the engineering team to bring Microsoft Whisper caption generation into the existing Vantage media pipeline.

My work covered the Publishing Operations side of the system:

- Defined requirements and production milestones
- Kept caption completion outside the publishing-completion gate
- Ran UAT and approved production releases
- Built a regression framework to catch caption-quality drift across formatting changes
- Reviewed post-launch patches and coordinated adoption with European operations

The partner launch report measured turnaround at about 10 minutes, down from 24 hours. Additional production languages followed after the English rollout.

### PastForward Description Generation

**Role:** Prompt and harness engineer  
**Scope:** Batch generation, validation, cost modeling, and publication  
**Stack:** Python, Anthropic Messages API, YAML validation rules, Cosmo

PastForward regenerated editorial descriptions for the LinkedIn Learning back catalog.

I engineered the prompts and Python harness used to process the content through the Anthropic API. The workflow included:

- Structured request and response handling
- Output validation rules
- Cost modeling before full processing
- A 500-video pilot
- Publication of validated descriptions to Cosmo

The team generated and published roughly 54,000 video descriptions through the workflow.

### Semantic Skill Mapping — Integration Guidance

**Role:** AI integration advisor  
**Scope:** Testing strategy, validation, deployment readiness, and system integration  
**System context:** Python, vector embeddings, Anthropic Messages API

The internal Taxonomy team developed a workflow that uses vector embeddings and Anthropic API classification to map customer terminology to the LinkedIn Learning skills taxonomy.

I helped the team:

- Shape test plans and validation scenarios
- Review how uncertain suggestions reached editorial review
- Assess deployment readiness and operational risks
- Align the AI workflow with surrounding content-management systems
- Define the broader integration strategy

This was an advisory and integration role. I did not build the taxonomy normalizer.

### LXG Cosmo Tools

**Role:** Primary maintainer and platform developer  
**Scope:** Content operations, safe bulk updates, agent interfaces, and distribution  
**Stack:** Python 3.12, Click, REST APIs, pytest, GitHub Releases

`lxg-cosmo-tools` gives content teams a command-line interface to LinkedIn Learning's content-management system.

The command surface covers projects, tasks, courses, captions, categories, learning paths, filter views, and bulk transformers. The tool is designed for both direct use and agent-guided workflows:

- Structured JSON output for reliable tool consumption
- Test-environment defaults for safer exploration
- Validation safeguards for bulk changes
- Retryable failure files for partial operations
- Bundled command and field references
- Pytest regressions for API response handling, CLI behavior, and skill installation

The goal is not to make an agent guess how the content system works. The CLI provides a defined interface, and the bundled instructions teach agents how to use it.

### Publishing Services API

**Role:** Backend and platform developer  
**Scope:** Publishing metadata, validation, media actions, document artifacts, and operator access  
**Stack:** Python, FastAPI, Pydantic, REST APIs, Linux, Azure

I rebuilt and extended a shared publishing API that supports course metadata, media operations, ingest validation, and PDF/JSON artifacts.

Platform work included:

- Environment-based Pydantic configuration
- Certificate and service-authentication support
- Validation endpoints shared by multiple workflows
- Severity-based notifications
- Managed Linux VM deployment
- Self-service access that reduced routine server logins
- Copy-failure recovery and service-health alerts

### URL Resource PDF Workflow

**Role:** Project lead and workflow integrator  
**Scope:** Editing, Publishing Operations, production management, and accessibility review  
**Stack:** Python, PDF generation, Pacman, publishing APIs

Course URLs had been burned into videos, making them difficult to update and impractical for screen-reader users.

I led the move to downloadable URL-resource PDFs:

- Started with a written workflow proposal
- Coordinated the decision with Editing, Publishing Operations, and Trust & Equity
- Integrated PDF publishing into Pacman
- Added automatic republishing on release day

The rollout replaced burned-in URL overlays and removed manual PDF uploads. Accessibility claims remain limited to the reviewed technical components and do not cover every course asset.

### Media Analysis and Quality Tooling

**Role:** Developer  
**Scope:** Inspection, delivery decisions, and cloud studio workflows  
**Stack:** Python, PyMediaInfo, FFmpeg, VMAF, HLS/DASH

I built reusable media-analysis tools for production teams:

- A MediaAnalysis API built with PyMediaInfo
- Video inspection reports generated from FFmpeg and MediaInfo
- VMAF-based analysis used to inform HLS/DASH encoding decisions
- Validation utilities for source media and publishing packages

These tools turned media inspection into repeatable APIs and reports instead of one-off command-line analysis.

### Media Archiving ETL

**Role:** Pipeline developer  
**Scope:** Asset classification, archive reporting, metadata, and storage transitions  
**Stack:** Python, SQL, file-system metadata, scheduled ETL

I developed a Python ETL pipeline for archive and storage-usage reporting. The system identifies eligible content using age, publication status, and operational metadata, then prepares the information needed for archive transitions.

This replaced manual classification and gave post-production teams a repeatable view of archive candidates and storage usage.

## Platform Leadership

### Cross-Region Tooling Program

I founded a tooling program spanning North America and Europe after finding production scripts and extensions scattered across individual machines.

The program established:

- Shared repositories and naming conventions
- Named owners for production tools
- Documentation and onboarding guidance
- A tiered model for experimental, shared, and managed tools
- A working relationship with engineering centered on mentorship and risk review

Eleven production tools were under version control by the end of March 2025.

### Minimum Viable Trust

As AI-assisted development made it easier for non-engineers to create internal tools, I wrote an multi criterion review framework covering ownership, users, maintenance, documentation, source control, backups, security review, peer review, succession, and engineering involvement.

The framework gave managers, builders, and engineering teams a shared way to decide when a prototype was ready to support production work.

### Platform and Workflow Taxonomy

**Role:** Technical lead and cross-team advisor  
**Scope:** Internal tools, production studio filesystems, CMS states, and AI integrations

I guide taxonomy and naming decisions across the systems used to produce and publish content. This work is separate from the semantic skill-mapping project.

The shared vocabulary covers:

- Tool categories such as scripts, services, skills, and managed applications
- Production filesystem names and workflow-oriented folder boundaries
- CMS contract types, status fields, and publishing handoffs
- Ownership and lifecycle expectations for AI-enabled tools

Regional teams can use the same terms, ownership boundaries, and handoff points when they design new workflows.

## Studio AI Integration Prototypes

I built this family of public prototypes to explore a practical question: where should a model help in a studio workflow, and where should ordinary software remain in control?

The applications share a small agent core, stable machine-readable interfaces, deterministic validation, offline test paths, and per-run telemetry. Together they cover agent observability, caption repair, editorial change lists, delivery conformance, and production-tracking queries.

These are public prototypes and reference implementations, not claims that they are deployed at a studio.

### [ReplyKit](https://github.com/eggy-sh/replykit)

**Role in the family:** Shared agent I/O engine  
**Stack:** Python, provider adapters, structured tool calls, token/cost telemetry

ReplyKit is the common layer beneath the post-production tools. It gives each application the same model interface, tool registry, bounded repair loop, and usage telemetry without binding the application to one model provider.

**Benefit:** A studio tool can change model providers without rewriting its business logic. Malformed tool calls follow a bounded repair path, and every call reports tokens, estimated cost, and repair attempts.

### [Agent Heart](https://github.com/eggy-sh/agent-heart)

**Role in the family:** Observability and oversight for agent-run tools  
**Stack:** TypeScript, CLI and SDK, HTTP API, SQLite

Agent Heart tracks a tool call from start through heartbeat and completion. It distinguishes active, stale, dead, failed, and completed-but-unverified work, including parent/child task trees.

It also records duration, token use, cost, and verification status. Commands can be wrapped without changing their implementation.

**Benefit:** Long-running agent workflows stop being silent processes. Operators can see what started, where a run stalled, which child task failed, and whether completed work still needs review.

### [Subtitle Medic](https://github.com/eggy-sh/subtitle-medic)

**Role in the family:** Caption QA and cue-scoped correction  
**Stack:** Python, SRT/WebVTT, glossary validation, ReplyKit

Subtitle Medic checks caption structure and readability, then optionally sends only flagged cue text to a model for correction.

Timing, cue indexes, and cue count remain outside the model's control. The full document is validated again before output, and glossary terms are checked after correction.

**Benefit:** A caption workflow can use language models for text cleanup without risking timeline drift or malformed deliverables. The deterministic QA path works without a model or network connection.

### [Cutlist](https://github.com/eggy-sh/cutlist)

**Role in the family:** Editor notes to timeline-ready change lists  
**Stack:** Python, OpenTimelineIO, CMX3600 EDL, Frame.io exports, ReplyKit

Cutlist turns free-form editor or director notes into discrete change requests with actions, rationales, source references, confidence, and frame-accurate timecodes.

The model interprets the prose. Deterministic code performs the timecode math and writes OpenTimelineIO and EDL files that editorial systems can import.

**Benefit:** Assistant editors spend less time transcribing review notes into a timeline. Each change remains traceable to its source, and the exported formats are validated by reading them back through editorial parsers.

### [Conforma](https://github.com/eggy-sh/conforma)

**Role in the family:** Media and editorial-sequence conformance  
**Stack:** Python, YAML specifications, ffprobe/MediaInfo JSON, OpenTimelineIO, ReplyKit

Conforma checks rendered media against delivery requirements such as resolution, frame rate, codec, bit depth, audio layout, and container. It also checks exported timelines for slate length, muted reference audio, and track layout.

Pure rule functions produce the pass/fail result and concrete fix commands. A model may explain the report or classify an ambiguous track role, but it cannot override a deterministic failure.

**Benefit:** Delivery specifications become versioned data that can run in CI or a studio pipeline. The same rules work with ffprobe or MediaInfo output and across OTIO-supported editorial formats.

### [Slack Glue](https://github.com/eggy-sh/slack-glue)

**Role in the family:** Natural-language access to production tracking  
**Stack:** Python, Slack Events API, validated query schemas, mock ShotGrid, ReplyKit

Slack Glue translates a producer's plain-language request into a strict query schema and executes it against production-tracking data.

The model selects only from allowed endpoints, fields, and enum values. Deterministic code validates the query, retrieves records, counts results, and formats the reply. Unsupported terms produce a targeted clarification instead of an invented answer.

**Benefit:** Producers can ask operational questions where they already work without giving a language model authority over the system of record.

### Shared Design Principles

- Put models at the ambiguous language boundary, not in charge of deterministic truth
- Use stable JSON and domain objects between agent and application layers
- Preserve source provenance and make uncertainty visible to operators
- Keep tests hermetic with scripted or local model substitutes
- Track token use, cost, repair attempts, and verification status per run
- Export formats that existing studio tools already understand

## More

- [Profile](README.md)
- [Résumé](RESUME.md)
- [LinkedIn](https://linkedin.com/in/ehernandez0/)
- [GitHub](https://github.com/eggy-sh)
