# Verify company hiring before your agent acts

**Give your agent an official company website. Get dated job openings, source evidence and an explicit coverage result for up to $0.03 per company.**

For account-research and recruiting agents that already have a company shortlist: use [Verified Hiring Signals](https://apify.com/impressionable_lupine/company-recent-job-openings) to check recent live openings before adding hiring context to a report or research queue. The result is structured JSON, not a page dump. This service checks supplied companies; it does not discover prospects, identify people or prove buying intent.

Built by Majd Hijazin / Boatify Rentals LLC. The publisher owns the routed paid Actors and can earn revenue from eligible use. The skill and examples are free; executing an Actor requires the caller's spending approval. Seven public capabilities are listed below, with **Hiring as the suggested first trial**. This recommendation is based on release evidence, not proven demand.

## Start with one company: maximum $0.03

Try this instruction in an agent that has installed the skill below and connected to Apify MCP:

> Check https://linear.app for live openings published or republished in the last 30 days, return at most five jobs, and spend at most $0.03 from my authorized funded account. Check the current price first. Preserve source URLs and observation times; keep incomplete coverage separate. Do not contact anyone or enable monitoring.

Choose your own official company website for a real trial. The Linear input is a worked example, not a guarantee of current results. One company per run. Review the input limits and evidence rules in [SKILL.md](SKILL.md).

**Before paying:** connect to `https://mcp.apify.com?tools=actors,runs,storage`, use the client's secure authentication, and run read-only `fetch-actor-details` for `impressionable_lupine/company-recent-job-openings`. Confirm the exact public Actor, the available pinned build `2.0.18`, `$0.03` per `verified-report`, and standard platform usage included. Missing or changed terms mean stop before purchase. Installing the skill or reading this page is not spending authorization.

The bounded MCP call, after the caller authorizes it:

```json
{
  "name": "call-actor",
  "arguments": {
    "actor": "impressionable_lupine/company-recent-job-openings",
    "input": {
      "company_website": "https://linear.app",
      "lookback_days": 30,
      "max_jobs": 5
    },
    "waitSecs": 30,
    "callOptions": {
      "build": "2.0.18",
      "memory": 512,
      "timeout": 120,
      "maxTotalChargeUsd": 0.03
    }
  }
}
```

Save the returned run ID and reconcile that same run with `get-actor-run`. Once it succeeds, retrieve `OUTPUT` with `get-key-value-store-record` from that run's `defaultKeyValueStoreId` (`recordKey: "OUTPUT"`), or its default dataset with `get-dataset-items`, limit 1. A slow response is not permission to purchase again. Match Actor/build/input and validate the full report before using it.

## What a real observed result looks like

The following is an **abbreviated projection of an owner-funded release test**, observed **2026-10-08 05:55 UTC**, run `AvHmizrbPI5b0feZa`, build `2.0.18`. It is dated evidence, not a new live response, a customer purchase or an exhaustive list of Linear jobs. Five jobs were returned; two are shown here. `last_published` can mean republication rather than first posting.

```json
{
  "company_website": "https://linear.app/",
  "checked_at": "2026-10-08T05:55:20.615Z",
  "status": "success",
  "signal_status": "verified_recent_openings",
  "coverage_complete": true,
  "job_count": 5,
  "jobs_sample": [
    {
      "title": "Account Executive, Enterprise",
      "location": "Singapore",
      "published_date": "2026-10-06T00:55:56.942Z",
      "date_meaning": "last_published",
      "source_url": "https://jobs.ashbyhq.com/Linear/6dd5500a-4bd4-4f57-ba09-7b07acefecf4",
      "checked_at": "2026-10-08T05:55:21.357Z"
    },
    {
      "title": "Account Executive, Growth ",
      "location": "Singapore",
      "published_date": "2026-10-06T00:26:55.003Z",
      "date_meaning": "last_published",
      "source_url": "https://jobs.ashbyhq.com/Linear/cb8e77a6-4316-45c6-ac8d-7ade980cd65e",
      "checked_at": "2026-10-08T05:55:21.357Z"
    }
  ]
}
```

## Decide what the result permits

| Outcome | Safe use by the agent | Report-event charge |
|---|---|---|
| Complete-positive | Cite the observed recent jobs within the checked source scope; respect output truncation. | Up to $0.03 |
| Partial-positive | Cite the verified jobs and disclose incomplete coverage. | Up to $0.03 |
| Scoped complete-negative | Say no recent dated jobs were verified within the checked scope/window; do not say the company is not hiring. | Up to $0.03 |
| Unknown / invalid input | Keep the company unresolved; do not invent a negative. | No report event |

Empty jobs alone do not establish a negative. Source timestamps, `coverage_complete`, `coverage_scope`, errors and truncation matter. Supported public careers/linked ATS sources can be unavailable or lack verifiable dates. A title filter on the returned jobs is a caller-side step; the Actor has no department/geography/title-filter input, and a capped result cannot prove that an unreturned role is absent.

Why pay: one small call returns normalized jobs with verifiable dates, primary-source links, evidence hashes and explicit uncertainty. This can save source-specific acquisition and verification work. Use a direct ATS API instead when you already know the board and only need its raw jobs; choose broader discovery or people-data tools for other questions. No competitive cost or precision superiority is claimed.

## Expand only after a useful first result

For a separately authorized shortlist of ten distinct company websites, reserve at most **$0.30** and run sequentially with a **$0.03 cap per company**. This is the ordinary price, not a discount, coupon, free-credit offer or result guarantee. The caller must maintain durable reservations and same-run recovery; this repository does not automate batch purchasing or recurring monitoring. Model, hosting and payment-rail fees are separate from the included standard Actor usage.

Refresh only when the caller needs a new observation and authorizes the next spend. Preserve the previous snapshot for comparison; one snapshot does not measure hiring velocity. A later useful paid call is the repeat-use signal we want to measure. Downloads, owner tests, run counts and catalog submissions are not proof of revenue. Current independent purchases and repeat demand remain unverified.

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

[references/output-examples.json](references/output-examples.json) contains full unmodified reports from owner-funded tests on 2026-10-04, including original inputs and observation times. They are dated archives, not fresh results or independent customer purchases. [references/verification-notes.md](references/verification-notes.md) records schema checks and deployment gaps. Hiring and Contact correctness fixes were subsequently deployed and promoted to `2.0.18` / `0.2.2` after two owner-approved builds and six bounded owner-funded cloud tests on 8 October: positive/partial source-backed reports plus invalid unsafe-input checks, with runtime receipts and platform event counts verified. These checks used the Apify SDK/API, not live MCP/n8n execution. The 4 October archive stays unchanged. Read-only Actor/build/price checks were completed on 2026-10-08; the original Hiring/Contact installer check made no paid calls. The five additional public Actors passed owner-funded release builds and ten bounded source-positive/unsafe-input cloud checks on 8 October before publication. All seven public Actors then passed anonymous Store, runnable agentic Store filter and exact MCP metadata reads. None of these checks proves independent adoption, purchase settlement or profitability.

[capabilities.json](capabilities.json) is a descriptive index for routing these seven services, not a standardized payment manifest or proof of registry acceptance. Pricing and availability can change. No independent purchase, sale, profitability or repeat demand is claimed.

Community workflows are submitted for review: [Hiring/Contact](https://github.com/apify/awesome-skills/pull/149), [Vendor Evidence](https://github.com/apify/awesome-skills/pull/150), and [Pricing/Availability](https://github.com/apify/awesome-skills/pull/151). Submission is not catalog acceptance. This owner-maintained repository can be used directly; it is not an official Apify skill or an approved catalog entry.
