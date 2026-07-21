---
framework_version: 1.1.0
---

# Job Evaluation Framework

<!-- SETUP: Skill match areas and career goals are personalized by running /setup -->

## Eligibility Gate — run before scoring

If the candidate is not a citizen or permanent resident of the country they are applying in, run this first. It is a hard filter, not a scoring dimension, and it is separate from work-permit *timing*: timing asks "can they work the required hours yet?", eligibility asks "are they permitted to hold this job at all?". A candidate can pass timing and still be categorically excluded.

Read the posting's eligibility / work rights / "who can apply" section **verbatim** and classify:

| Posting wording | Verdict |
|-----------------|---------|
| Names a **citizenship or permanent-residency requirement** ("must be a citizen of X", "permanent resident", "PR required", "full working rights" where the employer means citizen/PR) | **FAIL — hard stop.** Do not score, do not draft. Quote the exact wording back to the user. |
| Requires a **security clearance** at any level | **FAIL** in most countries, since clearance is normally gated on citizenship. Verify the specific scheme rather than assuming. |
| **Explicitly names** the candidate's permit class, or says "international applicants welcome", "visa holders considered", "we sponsor" | **PASS** — verified acceptance. Worth noting as a positive in the application. |
| **Silent** on citizenship or residency | **PROCEED, but mark unverified.** Check the employer's own careers or international-applicant page before drafting. |

**Two rules that are easy to get wrong:**

1. **Silence is not permission.** Large graduate programs frequently gate eligibility on their own website rather than in the job ad. Highest-risk categories: professional-services firms, government and defence, banking, telecommunications, and anything touching critical infrastructure.
2. **A company-wide "we accept international applicants" statement is not role-level permission.** The common pattern is a general welcome followed by a *named list* of the specific programs or service lines it covers. Confirm the **specific posting or stream** appears on that list before drafting.

**Report an eligibility failure to the user with the quoted source** rather than silently dropping the role. They may know something about their own status that the profile does not record.

If the candidate's permit also constrains *hours* or *start date* (a student visa with a term-time cap, a permit that begins on graduation), record that as a second gate under this section during `/setup`, with the specific dates. Do not merge it with the eligibility question above — they fail for different reasons and need different answers.

A role that fails this gate is not scored and not drafted. Everything below applies only to roles that pass it.

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** Product strategy (0→1 launches, roadmapping, PWA architecture), commerce and payments (ONDC, settlement, reconciliation), growth optimization (checkout, conversion, coupon systems), user research and iteration, cross-functional leadership

**Moderate match areas:** Python and ReactJS (fluent enough to specify and review, not production-level engineering), technical architecture (understands systems but not a systems architect), data analysis (used secondary KPIs, but not a data analyst)

**Weak match areas:** Deep machine learning, DevOps/infrastructure, advanced backend systems, large-scale engineering leadership (5+ direct reports)

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** E-Commerce, Marketplace/Platform Products, AI Products, Strategy Consulting
**Moderate:** Payments and settlements, Logistics
**Entry-level:** Biotechnology, Media, Social, Gaming, Consumer, Finance, Healthcare, Other

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Department disorganization, work dominated by maintenance over development, poor chemistry with leadership, culture mismatches. Check reviews, media coverage, LinkedIn connections, and network contacts for insider perspective.

Also score (0-3): 0 red flags (layoffs, stale funding, shrinking space) · 1 early/unproven · 2 funded within ~24 months, credible investors, growing · 3 top-tier investors or profitable market leader. Purely about funding/stability — unrelated to product space. Normalise.

### 4. Location & Logistics (Pass/Fail + Notes)
- Within commute range: PASS
- Remote with occasional office: PASS
- Requires relocation: FAIL (deal-breaker)
- Frequent international travel: FLAG (discuss with user)

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- **Domain shift:** Explicitly moving AWAY from ONDC and transactional commerce; targeting frontier tech (AI/LLMs), deep tech (robotics, biotech, climate), and non-transactional consumer (social, content, behavior, wellness, edtech)
- **Culture signal:** Strong preference for teams with IIT alumni at founder/leadership level OR across the team (predicts better product culture)
- **Role direction:** Stay on product/strategy side; avoid hands-on technical engineering tracks
- **Company stage:** Prefer early-stage (Series A/B), 0→1 environments where ownership and product autonomy are highest
- **IIT presence (0–3) [IMPORTANT CULTURE SIGNAL]**: 
- 0: No alumni visible
- 1: Some alumni on team (engineers/product)
- 2: Alumni in leadership (VPs, heads of product)
- 3: IIT founder(s) OR founding team majority IIT AND recent hiring of IIT alumni across levels. This is a **strong positive signal** for product culture quality.

**Product space modifier (affects career motivation score)**:
- +8: Non-transactional consumer (social, content, behavior, wellness, edtech, creator economy) / frontier tech (AI/LLM) / deep tech (biotech, robotics, climate, space, defense) / behavioral psych-econ / applied research
- 0: Other spaces (SaaS, B2B tools, infrastructure, etc.)
- −5: Transactional/marketplace (e-commerce, payments, settlement, checkout, ONDC, high-churn). You're explicitly moving away from this.

Both signals are **critical for this candidate's motivation** — strong product culture (IIT presence proxy) + space alignment matter more than funding tier alone.

**Motivation filter:** Evaluate not just whether you *can* do the tasks, but whether the tasks will *energize* you. Consider:
- Tasks that energize: Building new products from zero, ambiguous problems, user research, navigating stakeholder disagreements, rapid iteration, shipping to learn
- Tasks that drain: Maintenance work on stable products, purely process-driven roles, low agency/high process, managing large established teams with entrenched ways
- Non-task factors: Leadership that encourages autonomy and rapid iteration; intellectual curiosity valued; fast-moving teams; clear user/data signals drive decisions

**Life situation alignment:** Consider personal constraints:
- **Security**: No current financial pressure; taking time to find next role that excites (projects ongoing)
- **Flexibility**: No relocation constraints within India; no time/family constraints mentioned
- **Professional development**: Strong interest in expanding domain knowledge (currently in commerce/payments; wants frontier/deep tech exposure)

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

Interpret results relative to the baseline defined in the data file's metadata. For index-based data, higher typically means above-market compensation.

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 20%
- Experience Match: 20%
- Behavioral Fit: 15%
- Career Alignment: 45%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
