# Agent Market: source-backed business intelligence for agents

Seven source-backed business capabilities for agents that already have official company websites. Built by Majd Hijazin / Boatify Rentals LLC. The publisher can earn revenue from eligible paid Actor use. This repository supplies a free integration skill; the underlying Apify services charge per eligible report.

## Choose the right capability

| Agent question | Exact public service | Event price |
|---|---|---|
| Which jobs has this company recently posted, with verifiable dates? | [Company Job Openings — Verified Hiring Signals](https://apify.com/impressionable_lupine/company-recent-job-openings) | $0.03 / `verified-report` |
| What plans and prices does this vendor display on its official pricing pages? | [SaaS Pricing Plans & Prices — Verified Reports](https://apify.com/impressionable_lupine/verified-saas-pricing) | $0.02 / `verified-pricing-report` |
| What price and stock evidence is published for this product and its observed variants? | [Product Price & Stock Availability — Verified](https://apify.com/impressionable_lupine/verified-retail-availability) | $0.01 / `verified-product-check` |
| Which public email, phone, contact-page and booking routes does this company publish? | [Website Contact Finder — Email, Phone & Booking](https://apify.com/impressionable_lupine/verified-contact-booking-signals) | $0.01 / `verified-contact-report` |
| Which named customer stories does this vendor publish on its official website? | [Customer Case Studies — Verified Vendor Evidence](https://apify.com/impressionable_lupine/verified-customer-proof) | $0.02 / `verified-customer-report` |
| Does this vendor publish a B2B partner program, and what next-step links are visible? | [Partner Program Finder — Verified B2B Evidence](https://apify.com/impressionable_lupine/verified-partner-programs) | $0.02 / `verified-partner-report` |
| Does this vendor officially document this named integration? | [Software Integration Checker — Official Evidence](https://apify.com/impressionable_lupine/verified-integration-evidence) | $0.02 / `verified-integration-report` |

Use Hiring to qualify an existing account research queue. Add Contact only when the caller requested contact enrichment. This does not discover companies, identify decision-makers, verify email deliverability, establish operating status or prove buying intent. Supported sources can be incomplete; unknown means inconclusive, not negative.

## Install the free agent skill

Requirements: Node.js 22.20.0 or newer, npm and Git. For Codex, in your project directory:

```sh
DISABLE_TELEMETRY=1 npx skills@1.7.1 add Hijazin/agent-intelligence-skills --full-depth --skill apify-company-hiring-contact --agent codex --copy --yes
```

For Claude Code, replace `--agent codex` with `--agent claude-code`. Inspect [SKILL.md](SKILL.md) and its references before installing. The installer is the external open-source [Vercel skills CLI](https://github.com/vercel-labs/skills); it is not our payment processor. Installing a skill does not authorize paid calls. Version 1.7.1 was checked against the official npm package repository. Documentation installation was tested on 2026-10-08 with Node.js 24.19.0 in isolated Codex and Claude Code project directories; all three workflows and twelve installed skill/reference copies matched the source exactly. This tests installation, not paid execution, independent adoption or settled payment.

Connect your MCP client to:

```text
https://mcp.apify.com?tools=actors,runs,storage
```

Use the client's secure Apify authentication. Do not paste tokens into chats, URLs, reports or skill files. The caller supplies funded capacity and an explicit spending cap. No subscription or automatic monitoring is started by this skill.

## Try a bounded question

> Check https://linear.app for recent live openings within 30 days, return at most five jobs, and spend at most $0.03. Preserve source evidence and separate partial coverage from complete findings.

> Find public contact routes on https://cliniquealpa.co.uk/, with evidence, spending at most $0.01. Do not email anyone or submit a booking form.

Exact Actor names, inputs, pinned builds and capped MCP argument templates are in [references/mcp-calls.json](references/mcp-calls.json). Read [SKILL.md](SKILL.md) for same-run recovery and budget reservation. The host must supply a durable ledger; this repository does not implement one.

## Choose an agent workflow

- [Hiring and public contacts](SKILL.md): qualify a supplied company research queue, then find contact routes only when requested.
- [Vendor evidence](skills/apify-vendor-evidence-check/SKILL.md): select official integration, customer-story or partner-program evidence for a vendor shortlist.
- [Cost snapshots](skills/apify-verified-cost-snapshots/SKILL.md): select SaaS plan prices or product price/stock evidence and preserve dated scope for comparison.

The `--full-depth` option is required to discover the nested workflows when a root SKILL.md exists. Install either additional workflow with the same command above, replacing `--skill apify-company-hiring-contact` with `--skill apify-vendor-evidence-check` or `--skill apify-verified-cost-snapshots`. Only public, validated Actors are routed here. Four other validated releases remain private because Apify returned daily-publication-limit-exceeded; they are not publicly callable and are excluded.

Prices checked 8 October 2026; re-read current metadata before purchasing. Standard Actor platform usage is included under the checked configuration. Your model, workflow hosting and external payment-rail fees are separate. Each new listed capability costs at most one eligible result event per bounded example: SaaS, Customer, Partner and Integration $0.02; Retail $0.01. Unknown/invalid outcomes do not produce a successful-result event. See each current Store README for exact billing policy. Ten Hiring checks cap at $0.30; caps are not discounts or positive-result guarantees.

## Evidence and limits

[references/output-examples.json](references/output-examples.json) contains full unmodified reports from owner-funded tests on 2026-10-04, including original inputs and observation times. They are dated archives, not fresh results or independent customer purchases. [references/verification-notes.md](references/verification-notes.md) records schema checks and deployment gaps. Later local runtime fixes are not assumed deployed. Read-only Actor/build/price checks were completed on 2026-10-08; the original Hiring/Contact installer check made no paid calls. The five additional public Actors passed owner-funded release builds and ten bounded source-positive/unsafe-input cloud checks on 8 October before publication. All seven public Actors then passed anonymous Store, runnable agentic Store filter and exact MCP metadata reads. None of these checks proves independent adoption, purchase settlement or profitability.

[capabilities.json](capabilities.json) is a descriptive index for routing these seven services, not a standardized payment manifest or proof of registry acceptance. Pricing and availability can change. No independent purchase, sale, profitability or repeat demand is claimed.

Community workflows are submitted for review: [Hiring/Contact](https://github.com/apify/awesome-skills/pull/149), [Vendor Evidence](https://github.com/apify/awesome-skills/pull/150), and [Pricing/Availability](https://github.com/apify/awesome-skills/pull/151). Submission is not catalog acceptance. This owner-maintained repository can be used directly; it is not an official Apify skill or an approved catalog entry.
