# Output Templates for Competitive Intelligence Agent

Use these templates verbatim unless I specify otherwise. Replace `{placeholders}` with concrete values.

---

## 1) Executive Brief (per company)

### {Company} — Tech & Market Update (as of {YYYY‑MM‑DD})

**What changed (deltas)**  
- [High] {delta one sentence} *(source: {url}, observed {date})*  
- [Medium] {delta one sentence} *(source: {url}, observed {date})*  
- [Low] {delta one sentence} *(source: {url}, observed {date})*  

**Tech strategy snapshot**  
- **Stack:** {languages / frameworks / cloud / data / deployment}  
- **Build vs Buy:** {stance or Unknown}  
- **Security:** {certs or Unknown}; incidents: {summary or None}  
- **AI/ML:** {notable models/tooling or Unknown}  
- **Partnerships:** {key partners}  

**Implications (for us)**  
1. {implication}  
2. {implication}  
3. {implication}  

**Recommended actions (owner → due date)**  
- {Action} — {Owner} → {Date}  
- {Action} — {Owner} → {Date}  

**Sources:**  
- {Title or page} — {url} *(observed {date})*  
- {Title or page} — {url} *(observed {date})*  

---

## 2) JSON Snapshot (per company)

Return a single JSON object that conforms to `CompetitiveScanCompanySnapshot` (see schema file). If any field isn’t verifiable, set its value to `"Unknown"` or `null` and include a verification note in the delta log.

```json
{
  "company": "{Company}",
  "as_of_date": "{YYYY-MM-DD}",
  "sources": ["{url1}", "{url2}"],
  "profile": {
    "founded": 2016,
    "employees": null,
    "ownership": "private",
    "funding": "Series C ($120M, 2023-09)"
  },
  "products": [
    {
      "name": "{Product A}",
      "categories": ["{Category}"],
      "key_features": ["{feature 1}", "{feature 2}"],
      "pricing_model": "tiered SaaS",
      "integrations": ["Salesforce", "Slack"],
      "roadmap_signals": ["Public beta of {feature}, 2025-08"]
    }
  ],
  "positioning": {
    "segments": ["Mid-market", "Enterprise"],
    "uvps": ["{UVP 1}", "{UVP 2}"],
    "go_to_market": "Direct + partners"
  },
  "tech_stack": {
    "languages": ["TypeScript", "Python"],
    "frameworks": ["React", "FastAPI"],
    "cloud": ["AWS"],
    "datastores": ["PostgreSQL", "Redis"],
    "infra": ["Kubernetes", "CDN"],
    "ml_ai": ["OpenAI APIs", "Hugging Face models"],
    "security_certifications": ["SOC 2 Type II"],
    "deployment": "SaaS",
    "proprietary_components": ["{component}"]
  },
  "strategy_signals": {
    "build_vs_buy": "Build core models; buy vector DB",
    "partnerships": ["AWS ISV", "Snowflake"],
    "mna": ["Acquired {Target}, 2025-07"],
    "patents": ["US1234567B2"],
    "oss_projects": ["github.com/org/{repo}"],
    "hiring_themes": ["Hiring for ML infra, security"],
    "risk_factors": ["High reliance on a single LLM provider"]
  },
  "customer_voice": {
    "themes_positive": ["Easy setup", "Quality support"],
    "themes_negative": ["Pricing confusion"],
    "notable_quotes": ["\"Great API coverage\" — G2, 2025-06"]
  }
}
```

---

## 3) Feature Matrix (portfolio)

Provide a compact markdown table with the specified features as columns and companies as rows. Use ✅ / ❌ / Unknown.

| Company | SSO | Audit Logs | On‑prem | SOC 2 | HIPAA | API Limits | Webhooks |
|---|---|---|---|---|---|---|---|
| {Company A} | ✅ | ✅ | ❌ | ✅ | ❌ | 120 req/min | ✅ |
| {Company B} | ✅ | ❌ | ✅ | ✅ | ✅ | Unknown | ✅ |
| {You} | ✅ | ✅ | ✅ | ✅ | ✅ | 600 req/min | ✅ |

> Note: If a claim is new or changed this run, add a footnote with source URL + observed date.

---

## 4) Pricing Table (per market or per vendor)

| Vendor | Free Tier | Entry Price (USD) | Pricing Model | Overage/Usage Notes | Source (Observed) |
|---|---:|---:|---|---|
| {Company A} | Yes | 19 / seat / mo | Tiered per-seat | Overages at $X per 1k calls | {url} (2025‑09‑05) |
| {Company B} | No | 249 / mo | Usage‑based | $Y per 1k events | {url} (2025‑09‑05) |

---

## 5) Delta Log (vs baseline)

List material changes since {baseline_date}. Classify by severity.

- **High** — Pricing, GA/EOL, major security cert, major outage/security incident  
- **Medium** — New integration/partner, notable leadership hire  
- **Low** — Docs tweaks, minor UI changes

```
[High] Pricing: Entry plan from $29 → $19 (source: {url}, observed {date})
[Medium] Integration: Added {Partner} (source: {url}, observed {date})
[Low] Docs: Updated API pagination limits (source: {url}, observed {date})
```

---

## 6) Tech Strategy Deep‑Dive bullets (when requested)

- **Architecture & Stack:** {summary}  
- **Proprietary vs Third‑Party:** {summary}  
- **AI/ML Footprint:** {models/services; training vs inference; safety posture}  
- **Security & Compliance:** {certs; bug bounty; incidents}  
- **Hiring Signals (last 6 months):** {themes with examples}  
- **Patents / OSS / Research:** {items and implications}  
- **Roadmap Signals:** {release notes; betas; conference talks}  

End with: **Top 5 implications** and **Top 5 recommended actions**.

---

## 7) Verification & Unknowns

For each field marked **Unknown**, add a one‑line **How to verify** step (e.g., “Check /pricing HTML, Wayback snapshot, or sales PDF”). Avoid guessing.

---

## 8) Severity Definitions (use consistently)

- **High:** Likely to change buying decisions or security reviews within a quarter.  
- **Medium:** Might affect evaluations or adoption within two quarters.  
- **Low:** Informational; unlikely to drive decisions alone.
