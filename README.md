# Evidence-backed business intelligence for agents

**Ask a specific question about a supplied company or product URL. Receive structured JSON with source evidence, observation times and explicit uncertainty. Eleven public Apify Actors, $0.01–$0.07 per eligible result.**

For account research, vendor evaluation and price monitoring workflows. Choose the capability that answers your question; inspect it for free before authorizing a paid call. These services check supplied websites and products. They do not discover company lists, identify decision-makers or prove buying intent.

Maintained by Majd Hijazin / Boatify Rentals LLC. We own the paid Actors and can earn eligible usage revenue. This repository and its skills are free; Actor execution uses the caller's authorized Apify account.

**Website:** [agents.retainly.dev](https://agents.retainly.dev) has task guides, recorded examples and an agent quickstart. Its [llms.txt](https://agents.retainly.dev/llms.txt) and [capabilities.json](https://agents.retainly.dev/capabilities.json) currently cover seven Actors; use the [eleven-Actor routing index in this repository](capabilities.json) for the full public portfolio. Always recheck live Apify metadata before a paid call.

## Choose by the question you need answered

| Question / capability | What comes back | Price per eligible report | Key limit |
|---|---|---|---|
| [Recent company job openings](https://apify.com/impressionable_lupine/company-recent-job-openings) · `job.find` | Dated live jobs, primary-source URLs, date meaning and coverage | $0.03 | Checks a supplied company; one snapshot does not measure hiring velocity |
| [Website contact finder](https://apify.com/impressionable_lupine/verified-contact-booking-signals) · `contact.find` | Public email, phone, contact-page and booking routes with evidence | $0.01 | Verifies publication, not deliverability, person identity or completed booking |
| [SaaS pricing plans](https://apify.com/impressionable_lupine/verified-saas-pricing) · `pricing.check` | Observed plan names and displayed prices with source and coverage | $0.02 | Dynamic, regional, checkout or tax details can remain unknown |
| [Product price and stock](https://apify.com/impressionable_lupine/verified-retail-availability) · `product.check` | Published product/variant offers and availability evidence | $0.01 | Does not complete checkout; an unobserved variant price remains null |
| [Customer case studies](https://apify.com/impressionable_lupine/verified-customer-proof) · `customer.evidence` | Named customer stories linked from the vendor's official website | $0.02 | Vendor statements, not independent endorsement or proof a relationship is current |
| [B2B partner programs](https://apify.com/impressionable_lupine/verified-partner-programs) · `partner.find` | Official program evidence and published next-step links | $0.02 | Does not establish eligibility, apply or infer acceptance |
| [Software integration checker](https://apify.com/impressionable_lupine/verified-integration-evidence) · `integration.verify` | Official evidence for a supplied integration name | $0.02 | Documentation is not a tested connection or proof of plan entitlement |
| [Qualified B2B company enrichment](https://apify.com/impressionable_lupine/qualified-b2b-lead-finder) · `lead.enrich` | Supplied-domain company and public business contact evidence | $0.07 per qualified lead | Does not identify people or guarantee email deliverability |
| [Company capability claim check](https://apify.com/impressionable_lupine/verified-company-capability-claims) · `claim.verify` | Scoped status for a specified API, partner or integration claim | $0.02 | Official documentation is not proof an integration works in a customer's account |
| [Company product updates](https://apify.com/impressionable_lupine/verified-company-updates) · `company.updates` | Dated, official product updates and source links | $0.02 | Coverage is limited to checked official sources and date evidence |
| [Developer API docs finder](https://apify.com/impressionable_lupine/verified-developer-api-docs) · `api.docs.find` | First-party API documentation evidence and URLs | $0.01 | Public docs do not prove API access or plan entitlement |

Why pay: avoid maintaining source-specific acquisition, normalization and evidence checks for these narrow questions. Use a direct source API when you already have its adapter and only need raw data. Use a broader discovery or people-data provider for different questions. We have not established competitive cost or precision superiority, independent purchases or repeat demand.

**[Seven archived full examples and capped API/MCP calls](references/validated-examples-2026-10-08.json)** · **[Machine-readable routing index for all eleven](capabilities.json)**. The four newer public Actors have bounded Store example tasks for [lead enrichment](https://apify.com/impressionable_lupine/qualified-b2b-lead-finder/examples/verify-one-clinic-business-lead), [claims](https://apify.com/impressionable_lupine/verified-company-capability-claims/examples/verify-linear-github-integration-claim), [updates](https://apify.com/impressionable_lupine/verified-company-updates/examples/check-intercom-product-updates), and [API docs](https://apify.com/impressionable_lupine/verified-developer-api-docs/examples/verify-linear-graphql-api-docs). Those saved examples are dated owner-funded runs, not customer purchases.

For an account research agent's first purchase decision, see the [one-company hiring check](references/one-company-hiring-check.md): exact task, $0.03 ceiling, a dated source-backed output and the interpretation limits.

## Inspect for free, then start with one company

Hiring and Contact live defaults checked **9 October 2026**. The other seven-service archive and its routing index were checked **8 October 2026**; prices, visibility and builds can change, so inspect again before spending. An anonymous metadata request does not start a run:

```sh
curl --fail --silent --show-error 'https://api.apify.com/v2/acts/DnTJ0PiYO5uNHgDKK'
```

For free MCP discovery, connect to `https://mcp.apify.com?tools=search-actors,fetch-actor-details` and inspect the exact Actor:

```json
{
  "name": "fetch-actor-details",
  "arguments": {
    "actor": "impressionable_lupine/company-recent-job-openings",
    "output": {
      "pricing": true,
      "inputSchema": true,
      "outputSchema": true,
      "metadata": true,
      "readme": true
    }
  }
}
```

Confirm the exact Actor ID, public status, available build, input schema, event price and included platform usage. Missing or changed terms mean stop before purchase. Reading this page, installing a skill or fetching metadata does not authorize spending.

Hiring is our suggested first trial for an existing company research queue, based on release evidence rather than proven demand. In a securely authenticated MCP client connected to `https://mcp.apify.com?tools=actors,runs,storage`, **after the caller authorizes up to $0.03**, use:

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
      "build": "2.0.20",
      "memory": 512,
      "timeout": 120,
      "maxTotalChargeUsd": 0.03
    }
  }
}
```

Equivalent API request, **only after the same spending authorization**. Set `APIFY_TOKEN` securely in your local client; never paste it into a chat, URL, report or repository:

```sh
curl --fail --silent --show-error \
  --request POST \
  --header "Authorization: Bearer ${APIFY_TOKEN}" \
  --header 'Content-Type: application/json' \
  --data '{"company_website":"https://linear.app","lookback_days":30,"max_jobs":5}' \
  'https://api.apify.com/v2/acts/DnTJ0PiYO5uNHgDKK/runs?build=2.0.20&memory=512&timeout=120&maxTotalChargeUsd=0.03&waitForFinish=30'
```

Choose your own official company website. The Linear input is a worked example, not a guarantee of current results. One company per run; title, geography and department filtering is a caller-side step, not a supported input. A capped response cannot prove that an unreturned role is absent.

For a one-click, one-company starting point, use the public [Hiring example task](https://apify.com/impressionable_lupine/company-recent-job-openings/examples/recent-hiring-sales-research), capped at $0.03 and pinned to build `2.0.20`, or the [Contact example task](https://apify.com/impressionable_lupine/verified-contact-booking-signals/examples/public-business-contact-booking-check), capped at $0.01 and pinned to build `0.2.4`. Check the displayed input and current billing terms before running either task in your own account. Their saved inputs are examples, not live result guarantees.

Save the returned run ID. If the response is slow or uncertain, reconcile that same run with `get-actor-run` (API: `GET /v2/actor-runs/{runId}`) before considering another purchase. Once it succeeds, fetch `OUTPUT` with `get-key-value-store-record` from its `defaultKeyValueStoreId` (`recordKey: "OUTPUT"`), or `get-dataset-items` from its `defaultDatasetId`. Read the envelope's `raw_report` and preserve its coverage, errors and billing receipt separately. Match Actor/build/input and validate the report before using it. **Do not automatically retry paid run creation.**

## Know what the evidence permits

The full downloadable examples are unmodified reports from **owner-funded SDK/API release tests on 8 October 2026**. Hiring returned five source-dated jobs at **08:40 UTC**, run `iccSKN2vi1E4Emrv7`, build `2.0.19`; Contact returned four published routes at **08:41 UTC**, run `Mb74YMiSOv2ehkyeL`, build `0.2.3`. The five other examples were observed around **05:12–05:14 UTC**. Each entry preserves the original input, timestamps, build, run ID and a report integrity hash.

These are dated observations, not new live responses, independent purchases or customer revenue. Hiring's `last_published` date can mean republication rather than first posting. Report billing fields may precede final event charging and do not by themselves prove a settled debit.

| Hiring outcome | Safe interpretation | Report-event charge |
|---|---|---|
| Complete-positive | Cite observed recent jobs within checked scope; respect truncation | Up to $0.03 |
| Partial-positive | Cite verified jobs and disclose incomplete coverage | Up to $0.03 |
| Scoped complete-negative | No recent dated jobs verified within the checked sources/window | Up to $0.03 |
| Unknown / invalid input | Unresolved; do not invent a negative | No report event |

For the other capabilities, charge eligibility follows the specific Store billing policy and evidence-bearing report outcome. Each bounded example allows at most one listed event. Unknown/invalid outcomes produce no successful-result event. Empty records alone are not proof of absence; inspect status, checked sources, source failures and coverage. A confidence or verification label is limited to the stated observation, not certainty about the whole business.

Standard Actor platform usage is included under the checked configuration. Your model, workflow hosting and external payment-rail fees are separate. A ten-company Hiring batch is at most **$0.30** only with ten separately capped runs, durable budget reservations and caller authorization. This is the ordinary price, not a discount or result guarantee. No subscriptions or recurring monitoring are started here.

## Install a workflow for your agent

Requirements: Node.js **22.20.0+**, npm and Git. Inspect [SKILL.md](SKILL.md) and its references first. For Codex, in your project directory:

```sh
DISABLE_TELEMETRY=1 npx skills@1.7.1 add Hijazin/agent-intelligence-skills --full-depth --skill apify-company-hiring-contact --agent codex --copy --yes
```

For Claude Code, replace `--agent codex` with `--agent claude-code`. The external [Vercel skills CLI](https://github.com/vercel-labs/skills) installs documentation; it is not our payment processor. Installation was tested on 8 October with Node.js 24.19.0 in isolated Codex/Claude Code projects; twelve installed skill/reference copies matched their sources. This was an installation check, not paid client execution or independent adoption.

Choose one workflow; `--full-depth` discovers the nested skills alongside the root skill:

- [Hiring and public contacts](SKILL.md): `--skill apify-company-hiring-contact`. Check recent jobs; add contact enrichment only when requested.
- [Vendor evidence](skills/apify-vendor-evidence-check/SKILL.md): `--skill apify-vendor-evidence-check`. Check an integration, customer story or partner program for a supplied vendor.
- [Cost snapshots](skills/apify-verified-cost-snapshots/SKILL.md): `--skill apify-verified-cost-snapshots`. Record SaaS pricing or product price/stock evidence for later comparison.

Use secure caller-managed Apify authentication for execution. A host must supply durable budget reservations and same-run recovery; this repository does not implement a purchasing ledger or authorize outreach, bookings, top-ups or monitoring.

## Verification record and open limits

[The seven-service archived examples](references/validated-examples-2026-10-08.json) include full reports and templates pinned to the defaults checked on 8 October. Their inputs and reports were validated locally against the checked schemas. The API/SDK release calls were tested; these copy-paste MCP templates have not been executed as a fresh live MCP/n8n purchase. Their historical build pins are preserved in the archive.

[The 4 October archive](references/output-examples.json) stays unchanged. Older workflow references retain their explicit earlier tested pins; they are historical examples, not statements of today's default. [Verification notes](references/verification-notes.md) preserve prior evidence and limits. Hiring/Contact defaults `2.0.19` / `0.2.3` add documentation to the previously fixed runtime; the latest two bounded release tests passed before this free documentation polish.

Eleven Actors are public as of the 9 October metadata check. The machine-readable routing index includes all eleven with the four newer live input/output schemas, prices and dated example links. The installed skill package still covers the original seven; use the direct Store links above for the four newer releases. The routing index is descriptive, not a standardized payment manifest. Direct x402 purchase, independent customer payment, repeat demand and profitability remain unverified.

Community submissions: [Hiring/Contact](https://github.com/apify/awesome-skills/pull/149), [Vendor Evidence](https://github.com/apify/awesome-skills/pull/150), [Cost Snapshots](https://github.com/apify/awesome-skills/pull/151). Submission does not establish catalog acceptance. This owner-maintained repository is usable directly; it is not an official Apify skill or a verified approved catalog entry.
