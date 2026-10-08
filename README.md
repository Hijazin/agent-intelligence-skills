# Agent Market: company hiring and website contact intelligence

Two source-backed business capabilities for agents that already have official company websites. Built by Majd Hijazin / Boatify Rentals LLC. The publisher can earn revenue from eligible paid Actor use. This repository supplies a free integration skill; the underlying Apify services charge per eligible report.

## Choose the right capability

| Agent question | Deliverable | Maximum report charge per company |
|---|---|---|
| Which supplied companies have recent live job openings? | Structured jobs with source links, publication dates/date meanings, checked time and explicit coverage limitations | $0.03 |
| What public contact routes does this supplied business advertise? | Website-observed email, phone, contact-page and booking links, with evidence | $0.01 |

Use Hiring to qualify an existing account research queue. Add Contact only when the caller requested contact enrichment. This does not discover companies, identify decision-makers, verify email deliverability, establish operating status or prove buying intent. Supported sources can be incomplete; unknown means inconclusive, not negative.

## Install the free agent skill

Requirements: Node.js 22.20.0 or newer, npm and Git. For Codex, in your project directory:

```sh
DISABLE_TELEMETRY=1 npx skills@1.7.1 add Hijazin/agent-intelligence-skills --skill apify-company-hiring-contact --agent codex --copy --yes
```

For Claude Code, replace `--agent codex` with `--agent claude-code`. Inspect [SKILL.md](SKILL.md) and its references before installing. The installer is the external open-source [Vercel skills CLI](https://github.com/vercel-labs/skills); it is not our payment processor. Installing a skill does not authorize paid calls. Version 1.7.1 was checked against the official npm package repository. Documentation installation was tested on 2026-10-08 with Node.js 24.19.0 in isolated Codex and Claude Code project directories; all four skill/reference files matched the source exactly. This tests installation, not paid execution, independent adoption or settled payment.

Connect your MCP client to:

```text
https://mcp.apify.com?tools=actors,runs,storage
```

Use the client's secure Apify authentication. Do not paste tokens into chats, URLs, reports or skill files. The caller supplies funded capacity and an explicit spending cap. No subscription or automatic monitoring is started by this skill.

## Try a bounded question

> Check https://linear.app for recent live openings within 30 days, return at most five jobs, and spend at most $0.03. Preserve source evidence and separate partial coverage from complete findings.

> Find public contact routes on https://cliniquealpa.co.uk/, with evidence, spending at most $0.01. Do not email anyone or submit a booking form.

Exact Actor names, inputs, pinned builds and capped MCP argument templates are in [references/mcp-calls.json](references/mcp-calls.json). Read [SKILL.md](SKILL.md) for same-run recovery and budget reservation. The host must supply a durable ledger; this repository does not implement one.

## Buy through Apify

- [Recent company job openings](https://apify.com/impressionable_lupine/company-recent-job-openings): `verified-report`, at most one $0.03 event per run. Eligible partial-positive and complete dated negative reports within checked scope can charge. Unknown/invalid checks do not produce a report charge.
- [Website public contact and booking routes](https://apify.com/impressionable_lupine/verified-contact-booking-signals): `verified-contact-report`, at most one $0.01 event per run for an eligible positive report. No-signal reports do not produce a report charge.

Prices checked 2026-10-08; re-read current metadata before purchasing. Standard Apify platform usage is included under the checked configuration. Your agent/model subscription, external MCP hosting and payment-rail fees are outside these report prices. Ten Hiring checks cap at $0.30; ten checks of both capabilities cap at $0.40. These are spending caps, not discounts or guarantees of ten positive findings.

## Evidence and limits

[references/output-examples.json](references/output-examples.json) contains full unmodified reports from owner-funded tests on 2026-10-04, including original inputs and observation times. They are dated archives, not fresh results or independent customer purchases. [references/verification-notes.md](references/verification-notes.md) records schema checks and deployment gaps. Later local runtime fixes are not assumed deployed. Read-only Actor/build/price checks were completed on 2026-10-08; no new paid execution was used to publish this package.

[capabilities.json](capabilities.json) is a descriptive index for routing these two services, not a standardized payment manifest or proof of registry acceptance. Pricing and availability can change. No independent purchase, sale, profitability or repeat demand is claimed.

A separate community contribution is [awaiting review in Apify's awesome-skills catalog](https://github.com/apify/awesome-skills/pull/149). This owner-maintained repository can be used directly; it is not an official Apify skill or an approved catalog entry.
