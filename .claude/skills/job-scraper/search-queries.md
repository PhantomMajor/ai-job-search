# Search Queries for Job Scraper

<!-- SETUP: Customize these queries based on your skills, target roles, and location -->

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Indian portals can be added via `/add-portal`. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

## Search Sites

Primary (your market's job boards):
- **linkedin.com/jobs** - LinkedIn job listings (filter: India / Delhi); also covered by `linkedin-search` CLI
- **freehir.io** - Indian job board; also covered by `freehire-search` CLI if installed
- **Company career pages** - Direct searches for target companies

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies (Airbnb, Stripe, Figma, etc.)

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies

## Query Categories

Queries are grouped by priority. Each query should be combined with your location terms (e.g. your city, region, or metro area) where the site supports it.

### Priority 1: Frontier Tech + Deep Tech + Non-Transactional Consumer (IIT-founded or IIT-heavy)

Strongest career direction: non-transactional consumer, frontier tech, deep tech with strong IIT presence.

```
site:linkedin.com/jobs "Product Manager" "AI" OR "LLM" OR "generative AI" India
site:linkedin.com/jobs "Product Manager" "deep tech" OR "frontier tech" India
site:linkedin.com/jobs "Product Manager" biotech OR "climate tech" OR "robotics" India
site:linkedin.com/jobs "Product Manager" IIT India
site:linkedin.com/jobs "Product" "IIT Bombay" OR "IIT Delhi" OR "IIT Kharagpur" India
site:linkedin.com/jobs "Head of Product" "early-stage" India -ONDC -"e-commerce" -marketplace -transactional
site:linkedin.com/jobs "Founding" "product" IIT India
```

### Priority 2: Non-Transactional Consumer (Social, Content, Behavior, Wellness - IIT presence)

Consumer-facing but behavioral/engagement-focused, not transactional. Strong product culture.

```
site:linkedin.com/jobs "Product Manager" "consumer" social OR content OR wellness OR edtech India
site:linkedin.com/jobs "Product Manager" "creator" OR "creator economy" India
site:linkedin.com/jobs "Product Manager" "community" India -ONDC -"e-commerce"
site:linkedin.com/jobs "Product" India -ONDC -"e-commerce" -"transactional" -payment -settlement -checkout
site:linkedin.com/jobs "IIT" founder OR leadership OR team India
```

### Priority 3: VC-Backed / Series A-B Early Stage (Strong Product Culture)

Early-stage (Series A/B) teams with founder-led product thinking.

```
site:linkedin.com/jobs "Product Manager" "Series A" OR "Series B" India
site:linkedin.com/jobs "Founding" "product" India
site:linkedin.com/jobs "0→1" product India
site:linkedin.com/jobs "Head of Product" "early stage" India -ONDC -"e-commerce"
```

### Priority 4: Broader Exploration (Product-Centric Companies)

Adjacent companies known for strong product culture.

```
site:linkedin.com/jobs "Product Manager" India site:stripe.com OR site:figma.com OR site:airbnb.com OR site:slack.com
site:linkedin.com/jobs "Product Strategy" India
site:linkedin.com/jobs "Consultant" "product" India
```

---

## **EXPLICITLY EXCLUDE**

Do NOT include in any search results:
- ONDC or ONDC-ecosystem companies
- E-commerce or marketplace platforms with a transactional focus
- Highly process-driven, mature companies with low product autonomy

## Location Filter

When evaluating results, verify the job location is within reasonable commute distance from your home. Define acceptable areas:
- **Delhi** (preferred, home base)
- **NCR region** (Gurgaon, Noida, Greater Noida - acceptable)
- **Remote or hybrid with Delhi office** (acceptable)
- **Other Indian metros** (acceptable with relocation consideration)
- **International** (consider timezone overlap for async work)

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
