# Edgar Hernandez

**Staff Engineer, Publishing Platforms & Applied AI**

[Email](mailto:h.edgar714@gmail.com) · [LinkedIn](https://linkedin.com/in/ehernandez0/) · [GitHub](https://github.com/edgarh92)

## Profile

Staff Publication Workflow Engineer building Python services, media pipelines, and applied AI workflows for LinkedIn Learning content systems across North America and Europe.

My work covers the full path from an operational problem to a supported system: requirements, API and data design, evaluation, deployment, rollout, monitoring, and incident recovery.

## Technical Expertise

- **AI and evaluation:** Anthropic Messages API, Microsoft Whisper, vector embeddings, prompt and evaluation harnesses, human review
- **Backend and data:** Python, FastAPI, Pydantic, REST APIs, PostgreSQL, MySQL, SQLite, JSON Schema
- **Media systems:** Telestream Vantage, FFmpeg, FFprobe, VMAF, PyMediaInfo, HLS/DASH
- **Platforms and reliability:** Linux, Azure, managed services, job monitoring, failure recovery, pytest
- **Architecture:** Event-driven pipelines, pluggable adapters, priority queues, validation gates, batch processing

## Experience

### LinkedIn — Staff Publication Workflow Engineer

**April 2025–present**

- Designed and own **Pacman**, a Python publishing orchestrator that connects content metadata, validation, queuing, and Telestream Vantage ingest for North American and European teams. Built reusable eligibility rules, priority scheduling, source/destination adapters, and self-service APIs.
- Added retry windows, failure summaries, editorial escalation, label-based exceptions, copy-failure recovery, and service-health alerts. Published operator documentation and a pipeline dashboard; no-touch ingest rose from 55.6% in September to 100% in December 2025.
- Built **lxg-cosmo-tools**, a Python CLI for project, course, caption, taxonomy, and bulk content operations. Structured JSON output and guarded bulk updates support safe use by scripts, agents, and non-engineering operators. Pytest regressions cover API response handling and command behavior.
- Guided taxonomy and naming decisions across internal tools, production studio filesystems, CMS workflow states, and AI integrations so regional teams used consistent terms and handoff points.
- Owned Publishing Operations integration, UAT, and release sign-off for **Microsoft Whisper within Telestream Vantage**. Built a regression framework to detect caption drift across formatting changes. The partner launch report measured turnaround at about 10 minutes, down from 24 hours.
- Engineered prompts and a Python harness for **PastForward**, helping the team generate and publish roughly 54,000 video descriptions through the Anthropic API. The workflow included validation rules, cost checks, and a 500-video pilot.
- Built semantic skill mapping that combines vector-embedding candidates with Anthropic API classification. Low-confidence suggestions go to editorial review, and accepted mappings become examples in later prompt context.
- Led a cross-team rollout that replaced burned-in video URLs with downloadable resources. Pacman publishes and republishes the PDF artifacts automatically, removing manual uploads from the release workflow.
- Migrated publishing APIs to managed Linux VMs, reducing dependence on workstation Python environments and giving operators self-service access without routine server logins.

### LinkedIn — Senior Workflow Engineer

**March 2021–April 2025**

- Owned Publishing Operations delivery for the Telestream Vantage platform migration, coordinating automated testing with the engineering team and the post-migration review.
- Founded a cross-region tooling program that brought 11 production tools into version control with named owners and documentation across North America and Europe.
- Created a reusable **MediaAnalysis API** with PyMediaInfo for cloud-based studio services and a Python ETL pipeline for archive and storage-usage reporting.
- Modernized captioning microservices to reduce dependence on a single vendor and expand language support.
- Built VMAF-based video-quality analysis to inform HLS/DASH encoding decisions for the LinkedIn Learning catalog.
- Developed media inspection and workflow utilities with Python, Bash, FFmpeg, and MediaInfo for remote production teams.

### Earlier LinkedIn Roles

- **Workflow Engineer** — February 2021–March 2021
- **Senior Compressionist** — September 2019–February 2021
- **Video Compressionist** — December 2016–September 2019

## Selected Systems

### Pacman Publishing Orchestrator

Python service that discovers publishing-ready content, applies eligibility and validation rules, schedules work, and submits media to Telestream Vantage. Regional requirements stay in reusable filters and adapters, avoiding duplicate pipelines.

### AI Captioning

Microsoft Whisper integration inside the Vantage workflow, with publishing gates kept independent from caption completion. The regression framework checks caption quality across formatting changes before production release.

### PastForward Description Generation

Prompt and API harness for batch description generation, validation, cost checks, and publication to Cosmo. The team used the workflow to generate and publish roughly 54,000 descriptions.

### Semantic Skill Mapping

Hybrid workflow combining vector embeddings and Anthropic API classification. Editorial reviewers handle uncertain suggestions, and accepted mappings improve later prompt context.

### LXG Cosmo Tools

Python CLI for content-management operations across courses, projects, captions, categories, learning paths, and bulk transformers. Includes test-environment defaults, JSON output, validation safeguards, retryable failure files, and bundled agent instructions.

### Platform and Workflow Taxonomy

Shared vocabulary for internal tools, production studio filesystems, CMS states, and AI integrations. The work aligns naming, ownership boundaries, and handoff points so regional teams can build automation against the same operating model.

## Education

**B.A., Radio-TV-Film**  
California State University, Fullerton · 2015

## Additional Material

- [Project portfolio](PROJECTS.md)
- [GitHub profile](README.md)
