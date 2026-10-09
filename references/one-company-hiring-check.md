# One company hiring check for an account research agent

**Question:** “Did this supplied company recently publish sales roles on its own careers site?” This is a source check for a company already in your queue, not company discovery or proof that the company intends to buy.

Start with the [public one-company example task](https://apify.com/impressionable_lupine/company-recent-job-openings/examples/recent-hiring-sales-research). It is pinned to Hiring build `2.0.20` and capped at **$0.03 total charge**. Use your own Apify account and inspect the task's current input, build, pricing and budget before starting it. The eligible event is one `verified-report` at $0.03; an unknown or invalid result does not emit that event. Standard Actor usage was included in the checked configuration. Your own workflow hosting, models and unrelated APIs are separate costs. Avoid automatic retries after an ambiguous run response; first reconcile the returned run ID.

For a custom company, send one official website, a lookback and a small result cap:

```json
{
  "company_website": "https://linear.app",
  "lookback_days": 30,
  "max_jobs": 5
}
```

Read the response's `status`, checked time, coverage, source URLs and `date_meaning` before using any job. A live job in a linked ATS with a recent `last_published` timestamp is a different claim from a recently *created* job. A source-scoped complete negative only covers the checked source and window. Blocked, undated or unsupported sources stay unknown. Do not turn either case into a claim about buying intent.

**Recorded example, not a live promise:** An owner-funded Apify SDK/API run on **8 October 2026** (run `iccSKN2vi1E4Emrv7`, build `2.0.19`) checked `linear.app` and reported an “Account Executive, Enterprise” listing in Singapore. Its evidence was Linear's linked [Ashby job page](https://jobs.ashbyhq.com/Linear/6dd5500a-4bd4-4f57-ba09-7b07acefecf4) and the public Ashby posting feed, with `date_meaning: last_published` and source timestamp `2026-10-06T00:55:56.942Z`. This shows the format and provenance as they were recorded; it does **not** say the job remains open today. The complete archived report, run metadata and API/MCP call templates are in [validated examples](validated-examples-2026-10-08.json).

If you need a list of companies to check, a person or email address, historical hiring velocity, or proof of purchase intent, use a separate provider or workflow. This Actor answers the narrower source-backed job question for a supplied company. Independent buyer payment, repeat demand and competitive precision superiority have not been verified.
