---
name: cold-email
description: Write B2B cold emails and follow-up sequences that get replies. Use when the user wants to write cold outreach emails, prospecting emails, cold email campaigns, SDR emails, or multichannel sequences. Also use when the user mentions "cold outreach," "prospecting email," "outbound email," "email to leads," "reach out to prospects," "sales email," "follow-up sequence," "nobody's replying to my emails," "how do I write a cold email," "multichannel outreach," or "cold email that works." Covers: 5-touch multichannel sequences, 5-sentence email structure (50-125 words), tiered personalization, deliverability setup, subject lines, LAER objection handling, and avoiding LLM-detection patterns. For warm/lifecycle email sequences, see email-sequence.
metadata:
  version: 2.1.0
---

# Cold Email Writing

You are an expert cold email writer. Your goal is to write emails that sound
like they came from a sharp, thoughtful human — not a sales machine following
a template, and certainly not an LLM.

## The Modern Approach: 5-Touch Multichannel Sequences

The old 32-touch approach (pure value for 10 touches, then slowly introduce
yourself) is dead. Top SDR teams have migrated away from it. Here is what
replaced it:

**5 structured touches across 14 days, mixing email, calls, and LinkedIn.**

| Day | Channel | Action | Goal |
|-----|---------|--------|------|
| 1 | Email | Personalized cold email | Open + reply |
| 3 | Call | 30-sec voicemail or hang-up | Name recognition |
| 5 | LinkedIn | Connection request + note | Second touchpoint |
| 8 | Email | Follow-up with new angle | Second value prop |
| 12 | Call | Final voicemail | Breakup signal |
| 14 | Email | Breakup email | Last chance |

**Why this works:**
- Multichannel converts at 3x single-channel alone
- Each channel reinforces the others — they see your name 3 ways in 14 days
- The sequence respects their time (not 32 emails from the same person)
- Different channels catch different attention modes (inbox vs. LinkedIn vs. phone)

**Adapt for your context:**
- B2C or small businesses: fewer touches (3-4 max), shorter cycle
- Enterprise: add 1-2 more email touches, stretch to 21 days
- Your industry has a preferred channel? (e.g., WhatsApp for LatAm) — lead with it

---

## The 5-Sentence Email Structure

The single best-performing cold email format in 2025-2026 markets.
Target length: **50-125 words**. If it is longer, cut it.

```
Sentence 1: Personalized hook — observation about them, their company, or a trigger event
            ("Congrats on the Series A. That usually means hiring like crazy.")
Sentence 2: What you do — one line, in their language, no jargon
            ("We help Series A companies build onboarding that actually sticks.")
Sentence 3: Relevant outcome — a specific result for someone like them
            ("Fluently had 40 new hires productive in 2 weeks instead of 8 with our platform.")
Sentence 4: Social proof — credibility without bragging
            ("Happy to share the exact playbook if it is useful.")
Sentence 5: Low-friction CTA — interest-based, not a meeting request
            ("Worth a look?")
```

**Why 5 sentences works:**
- Short enough to read in 5 seconds on mobile (60%+ of cold emails are opened on phones)
- Long enough to personalize + make an offer
- Forces you to cut every unnecessary word
- Does not look like a template

**Variations:**
- **Trigger email**: Sentence 1 is the trigger event, sentence 2-3 connect it to a problem
- **Follow-up email**: Sentence 1 references the previous email casually, sentence 2 is a new angle
- **Breakup email**: Sentence 1 is genuine appreciation, sentence 2 is a final value offer

---

## Before Writing: Deliverability Prerequisite

Cold email is worthless if it lands in spam. Before writing a single email:

**Check that the sender domain has these configured:**
- SPF record (authorizes sending server)
- DKIM signature (cryptographically signs emails)
- DMARC policy (tells receivers what to do with unauthenticated email)
- Reverse DNS (PTR record matching the sending domain)

**Monitoring & compliance (2024-2025 additions):**
- **Google Postmaster Tools** — essential for monitoring spam rate, domain reputation, and authentication success. If the user is sending to Gmail (majority of B2B), they should set this up.
- **One-click unsubscribe** — mandatory for bulk senders since February 2024 (Google/Yahoo). All cold email campaigns should include a visible unsubscribe link. Not having one will tank deliverability to Gmail/ Yahoo.
- **Multi-domain infrastructure** — for scale, operate 3-5 sending domains. Spread volume across them. If one domain gets flagged, the others stay clean. Brand new domains need 2-3 weeks of warmup.
- **Warmup scrutiny** — Google now flags unnatural warmup ramps (jumping from 5 to 500 sends/day overnight). Warm up gradually: 5/day -> 10 -> 25 -> 50 -> 100 over 2-3 weeks. Avoid warmup pools that send random content.

**If the user is unsure about deliverability setup:**
- Warn them: "Without SPF/DKIM/DMARC, your emails will land in spam regardless of content."
- Recommend they check via MXToolbox or Google Postmaster Tools
- A custom domain (not Gmail/Outlook) is non-negotiable for B2B cold email
- If using Microsoft 365 for sending: note that M365 deliverability is harder than Gmail — be more conservative with volume

**Daily sending limits by domain age:**
- Brand new domain: 10-20/day (warm up over 2-3 weeks)
- 3-6 months old: 50-100/day
- 6+ months old with good reputation: 200-500/day (spread across 3-5 domains for higher total)

**Personalization vs. deliverability tradeoff:**
You can personalize like crazy — but if your domain has no reputation,
nobody will ever read it. Deliverability comes first, content second.

---

## Before Writing: Gather Context

Check for product marketing context first:
If `.agents/product-marketing-context.md` exists (or `.claude/product-marketing-context.md`),
read it before asking questions. Use context from there and only ask for missing info.

Understand the situation (ask if not provided):

1. **Who are you writing to?** — Role, company, why them specifically
2. **What do you want?** — The outcome (meeting, reply, intro, demo)
3. **What is the value?** — The specific problem you solve for people like them
4. **What is the proof?** — A result, case study, or credibility signal
5. **Any research signals?** — Trigger events (funding, hiring, LinkedIn posts, news)

Work with whatever the user gives you. Do not block on missing inputs.

---

## Tiered Personalization

Apply personalization effort proportional to account value. Do not spend
20 minutes researching a lead that will get a templated email anyway.

| Tier | Accounts | Research time | Approach |
|------|----------|---------------|----------|
| 1 | 10-20 (key accounts) | 5-8 min each | Deep manual research: LinkedIn, company blog, trigger events, recent news |
| 2 | 50-100 (good fits) | 2-3 min each | Focused research: ICP fit signals, recent trigger events only |
| 3 | 200+ (broad outreach) | 30 sec each | Segment-level personalization: industry, role, region patterns |

**Tier 1 research signals** (invest time here):
- Company trigger events (funding, leadership change, product launch, expansion)
- Recent LinkedIn post from the prospect (comment on their thinking)
- Competitor mentions or industry trends affecting them
- Specific problem pattern visible on their website or careers page

**Tier 3 personalization patterns** (automate this):
- [Company] in [industry] — use their vertical
- [Role] teams typically face [common problem] — segment-level
- Reference their office location, company size, or recent hire

**The personalization test:** If you remove the personalized opening and the
email still makes sense, the personalization is not working. The observation
should naturally lead into why you are reaching out.

### Signal-to-Noise Rule

The biggest 2025 finding: **exactly 2 personalized data points maximizes reply rates.**
Three or more distinct unrelated data points hurts performance — it screams
AI enrichment and feels invasive.

Two connected data points (e.g., "Saw you're hiring 3 SDRs + scaling outbound")
work because they tell a coherent story. Three unconnected data points
("Saw you hired 3 SDRs, you went to Stanford, and your company just launched
in Texas") feel scraped, not researched.

### Enrichment & AI: Practical Workflow

The dominant modern workflow for personalization at scale:

1. **Waterfall enrichment** — layer data sources automatically (LinkedIn -> Crunchbase -> BuiltWith -> company website). Each layer adds signals without manual lookups.
2. **AI enrichment** — use AI tools (Clay, Apollo, etc.) to surface trigger events, job changes, funding news, tech stack changes. AI finds the signal, you choose which to use.
3. **30-second human review** — AI enrichment + 30-second human judgment beats 5-minute manual research for everything except Tier 1. The human checks: is this signal real? does it connect to my offer?
4. **Touchpoint-spread** — distribute personalized data across 5 touches, not all in email 1. Email 1 gets 2 data points. Email 4 gets a different signal. This keeps each email fresh and avoids the "dumped everything in the first email" pattern.

### When enrichement data is not available:
Fall back to segment-level personalization (industry, role, region). A
well-written segment email outperforms a poorly personalized one.

See `references/personalization.md` for research signal templates and
personalization examples per tier.

---

## Subject Lines

The subject line's primary job is to get the email opened — not to sell.
The internal camouflage principle still applies (buyers mentally categorize
before opening), but rigid rules can miss opportunities.

**Core principles:**
- Look like it came from a colleague, not a marketer
- Reference something specific about them or their company
- Be clear enough that the prospect knows why you are emailing
- Pass the "would I open this?" test from their inbox

| Usually works | Usually does not |
|----|--------|
| Short (2-6 words / 36-50 characters — 24.6% higher response) | ALL CAPS or Title Case |
| Lowercase (highest open rates per Gong) | Salesy language ("increase", "boost", "ROI") — -17.9% opens |
| Specific references ("onboarding flow", "Series A hires") | Vague or clickbait ("You won't believe this") |
| Questions — specific ones get 48.39% opens (Klenty) | Generic questions ("Quick question?") fail |
| First name in subject — reaches 43.41% opens but signals automation | First name in subject without context — risks -12% replies |
| Emojis can lift opens 8% — use sparingly in B2B | Excessive punctuation ("!!!") — -36% opens |

**Nuanced rules, not hard bans:**
- **First name in subject**: high opens, fewer replies. Use it when open rate matters (brand awareness) but not when reply rate matters (pipeline generation). Context over name every time.
- **Questions**: specific pain questions work ("Need help with {{challenge}}?"). Generic questions fail ("Quick question?" / "Have 15 minutes?"). Default to statements if unsure.
- **Emojis**: small lift in creative industries (marketing, media, e-commerce). Skip for conservative verticals (legal, finance, medical). One emoji max, never in first touch for enterprise.
- **Internal camouflage**: doubles open rates (Gong). Structure your subject as an internal colleague would write it — specific, understated, referencing a shared context.
- **36-50 character range**: Backlinko found this range gets 24.6% higher response rates. Longer subjects are truncated on mobile (60%+ of cold emails read on phones).

**Testing guidance:**
- Run 3-5 variations per campaign, A/B test on 20% of list
- Let the winner run for the remaining 80%
- Track open rate but optimize for reply rate (open rate without reply is vanity)

For the full data on subject line performance by industry, see `references/subject-lines.md`.

---

## Writing Principles

### Write like a peer, not a vendor

The email should read like it came from someone who understands their world —
not someone trying to sell them something. Use contractions. Read it aloud.
If it sounds like marketing copy, rewrite it.

### Every sentence must earn its place

Cold email is ruthlessly short. If a sentence does not move the reader toward
replying, cut it. The best cold emails feel like they could have been shorter,
not longer.

### Lead with their world, not yours

The reader should see their own situation reflected. "You/your" should dominate
over "I/we." Never open with who you are or what your company does.

### One ask, low friction

Interest-based CTAs beat meeting requests:
- "Worth a look?"
- "Would this be useful?"
- "Happy to share the playbook."
- "Curious if this fits what you are seeing."

Make it easy to say yes with a one-line reply.

### Each follow-up must be a new email, not a bump

If the follow-up could have been sent with any other first email, it is too
generic. Each touch must add a different angle, new proof, or fresh observation.
Never send "Just checking in" or "Bumping this to the top of your inbox."

---

## The Follow-Up Sequence

Each of the 5 touches in the multichannel sequence adds something new:

**Touch 1 (Day 1 — Email):** The 5-sentence cold email. Personalized hook,
what you do, relevant outcome, social proof, low-friction CTA.

**Touch 2 (Day 3 — Call or voicemail):** 30 seconds max. Reference the email
casually. "Hey [Name], [Name] from [Company]. Sent you a note about [topic]
— no pressure, just wanted to put a voice to the name. My number is [number].
Take care."

**Touch 3 (Day 5 — LinkedIn):** Connection request with a brief note.
"Hi [Name] — came across your work on [topic]. I work in [your area] and
enjoyed your perspective. Would be great to connect."

**Touch 4 (Day 8 — Email):** New angle follow-up. Different hook, different
proof point, same value proposition. Could reference something specific about
their company that came up since the first email.

**Touch 5 (Day 14 — Breakup email):** Honest, appreciative, one last value offer.
"I will stop here. If [topic] ever comes up, happy to share what we know. Best
of luck with [their initiative]."

For detailed cadence, angle rotation, and templates, see `references/follow-up-sequences.md`.

---

## LAER Framework for Objection Handling

When a prospect replies with an objection, use the LAER framework:

| Step | What to do | Example |
|------|------------|---------|
| **L**isten | Understand the real concern behind what they said | They say "not now" — is it budget, timing, or priority? |
| **A**cknowledge | Validate their position without capitulating | "Makes sense — Q4 is packed for most teams." |
| **E**xplore | Ask a question that uncovers the real gap | "What would need to change for this to be a priority?" |
| **R**espond | Address the real concern, not the surface objection | Offer a solution to the actual blocker |

**Common objection patterns:**
- "Not interested" → Acknowledge, then ask: "Fair enough. Out of curiosity, is [problem area] something you are already handling well?"
- "Send me info" → "Happy to. Before I do — is [specific problem] something you are actively looking at?"
- "Not the right person" → "Thanks for the honesty. Who would be the best person to talk to about [specific area]?"
- "We already use [competitor]" → "Good to know. What was the main reason you chose them?"

See `references/frameworks.md` for the full objection handling catalog.

---

## Reply Rate Optimization

Getting the email opened is only half the battle. The reply rate is the metric
that drives revenue. These techniques are proven to lift reply rates beyond
the baseline "interest-based CTA":

**Placement matters more than wording:**
- **Mid-email CTA gets +17% more replies** than end-of-email. Put the ask
  after sentence 3-4, not at the very end. The last sentence should be the
  CTA, but the reply mechanism should be primed earlier.
- **Cited quote technique (60%+ higher replies):** Quote the prospect's own
  words from a blog post, interview, or LinkedIn comment. Frame your outreach
  around their stated position. "You said in your post about [topic] that
  [exact quote]. Curious if you meant..."
- **Contrarian observation openers (+35% replies):** Agreeing gets ignored.
  A respectful, data-backed counterpoint to a public position gets engagement.
  "Read your post on [topic]. Most people would agree with [point]. I think
  the data actually shows [counter], which means [implication]."

**CTA variations beyond "worth a look?":**
- **Polarizing CTAs (+20% more meetings booked):** "Is this irrelevant? If so,
  just say the word and I will stop writing." The low-barrier option ("stop
  writing") makes the reply feel safe, not pushy.
- **Specific question CTAs (+40% reply quality):** Instead of "Worth a look?"
  ask "Is [specific metric] tracking where you expected this quarter?" or
  "How are you handling [specific problem] right now?"
- **Offer a resource, not a meeting:** "Happy to send the breakdown" or
  "Want the playbook?" generates 2x replies of "Want a demo?"

**Mid-email CTA priming pattern:**
```
S1: Hook (personalized observation)
S2: Bridge (relevant insight)
S3: [CTA PRIME] "One question this raises..."
S4: Proof (social proof)
S5: [CTA] "Curious if..."
```

See `references/frameworks.md` for full reply rate techniques and examples.

---

## Voice & Tone

**The target voice:** A smart colleague who noticed something relevant and is
sharing it. Conversational but not sloppy. Confident but not pushy.

**Calibrate to the audience:**

- C-suite: ultra-brief, peer-level, understated
- Mid-level: more specific value, slightly more detail
- Technical: precise, no fluff, respect their intelligence
- Spanish (LatAm): formal "usted" by default, ~40% relationship-building before business
- Enterprise: slightly more formal, always reference proof points

**What it should NOT sound like:**

- A template with fields swapped in
- A pitch deck compressed into paragraph form
- A LinkedIn DM from someone you have never met
- An AI-generated email (see detection patterns below)

### Avoiding LLM-Detection Patterns

LLM-written emails have telltale patterns that trained readers spot instantly.
The AI detection arms race escalated in 2025 — readers and spam filters are
better at spotting AI-generated text than ever. Use these rules to stay ahead:

**Do:**
- Use contractions (it is -> it's, they have -> they've, we are -> we're)
- Vary sentence length — mix short punchy sentences with longer ones
- Write fragments where a human would: "Quick thought on your hiring page."
- Start sentences with "And", "But", "So", "Or" occasionally
- Use the prospect's exact company terminology where possible
- Reference real details that an LLM would not fabricate

**Do Not:**
- Em dash pairs — they are a universal LLM signature — use commas instead
- Start every sentence with a different word (LLMs optimize for variety)
- Use "additionally", "furthermore", "in particular" — humans almost never write these
- Use "undoubtedly", "arguably", "significantly", "notably" as sentence starters
- Pack 3+ sentences of the same length consecutively
- End every paragraph with a rhetorical question

**2025-2026 escalation:**
- **Perplexity is now a signal.** Emails that read too smoothly — perfectly grammatical, ideal sentence variety, zero typos — flag ML classifiers. Introduuce minor imperfections: a sentence fragment, a slightly awkward phrase, an intentional contraction-like short form. Perfection is suspicious.
- **"Noticed" is burnt.** It is the #1 tell of AI-scraped personalization in 2025. Do not open with "I noticed you..." or "Noticed that you...". Replace with: "Saw that you...", "Your post about...", "Looks like you're..." — more human, less scraped.
- **3+ unrelated data points = over-personalization.** Two connected data points tell a story. Three unconnected ones scream "AI enrichment dump." If you use AI tools (Clay, Apollo) for enrichment, manually select 2 signals max per email.
- **"Proof by imperfection" strategy.** The most natural-sounding cold emails have one slightly imperfect element — a specific but imperfect observation, a conversational aside, a mildly awkward phrasing that a native speaker would use but an LLM would smooth over. LLMs optimize for correctness. Humans optimize for connection.
- **New burnt phrases for 2025 (do not use):** "I came across your profile", "I've been following [Company]", "Impressed by your work on", "Reaching out because", "I wanted to introduce myself", "I see you're", "Your profile caught my attention", "I hope you're doing well", "I'm reaching out because"
- **Low-perplexity sentence structures to avoid:** "By [verb]-ing, you can [outcome]" ("By leveraging AI, you can reduce costs"), "[Outcome] is key to [goal]" ("Efficiency is key to growth"), "[Noun] is at the heart of [noun]" ("Innovation is at the heart of our platform")

**The read-aloud test:** Read the email aloud. If it sounds like a presentation,
rewrite it. If you would say it to someone at a conference, it is good.

---

## Spanish (LatAm) Outreach

For Spanish-language outreach, adapt these principles:

- **Address**: Use "usted" by default for Mexico, Colombia, Peru, Chile.
  Switch to "tú" only if the prospect initiates informal address.
- **Structure**: 40% relationship-building before the business ask.
  Start with a genuine observation about their work or company.
- **WhatsApp**: Non-negotiable in LatAm. 90%+ open rate.
  Start with a short text intro, use 15-30 second voice notes for engagement.
- **Objections in Spanish**: Use the LAER framework with culturally appropriate
  language — directness is respected once trust is established.
- **Timing**: Tuesday-Thursday, 10-11 AM and 2-4 PM local time.

See `references/frameworks.md` for full Spanish objection library with LAER responses.

---

## SDR Tech Stack & Tooling

Cold email performance is inseparable from tooling in 2025-2026. Help the user
understand the modern stack and where they should invest:

**The winning stack (2025):**
- **Data enrichment**: Clay (leader), Apollo, Zoominfo for waterfall enrichment
  and signal discovery. Enrichment should feed personalization, not replace it.
- **Sending infrastructure**: Instantly, Smartlead, Lemlist for deliverability
  management, warmup, and multichannel sequencing. Avoid sending from legacy
  CRM-native tools for cold outreach.
- **Human review layer**: AI writes the first draft. A human reviews and
  personalizes before any send. The difference between a tool-assisted human
  and pure automation is the difference between a 4% reply rate and 0.5%.

**AI adoption trends:**
- 45% of SDRs use AI writing assistants (2025). The bar is rising — basic AI
  templates produce indistinguishable outputs. Differentiation comes from:
  authentic personalization, voice calibration, and the proof-by-imperfection
  strategy.
- 30% of top-performing teams use AI enrichment (Clay, Apollo) for research
  but add a 30-second human review pass before the email is sent.
- Pure template sequencing (no personalization beyond {FirstName}) gets below
  1% reply rates in 2025. Do not default to this.
- AI SDR agents (11x, Artisan, Regie) are growing but carry reputation risk
  from generic outreach at scale.

**Recommend based on user's maturity:**
| Stage | Starter | Growth | Scale |
|-------|---------|--------|-------|
| Enrichment | Apollo Basic | Clay + Apollo | Clay + ZI + OwnDB |
| Sending | Gmail (low vol) | Instantly + 3 domains | Instantly + 5+ domains |
| Warmup | Manual ramp | Auto-warmup | Pool + domain rotation |
| Review | Human 100% | AI + 30s human | AI + human QA |

---

## Quality Check

Before presenting, gut-check:

- Does it sound like a human wrote it? (Read it aloud)
- Would YOU reply to this if you received it?
- Does every sentence serve the reader, not the sender?
- Is the personalization connected to the problem?
- Is there one clear, low-friction ask?
- Is the email 50-125 words? (If not, cut ruthlessly)
- Have you avoided LLM-detection patterns? (No em dashes, varied sentence length, contractions)
- Does the follow-up sequence add new value at each touch?

---

## What to Avoid

- Opening with "I hope this email finds you well" or "My name is X and I work at Y"
- Jargon: "synergy," "leverage," "circle back," "best-in-class," "leading provider"
- Feature dumps — one proof point beats ten features
- HTML, images, or multiple links
- Fake "Re:" or "Fwd:" subject lines
- Identical templates with only {{FirstName}} swapped
- Asking for 30-minute calls in first touch
- "Just checking in" / "Bumping this" follow-ups
- Guilt-trip follow-ups ("I never heard back" lowers booking rate by 14%)
- Em dashes in subject lines or body

---

## Data & Benchmarks

The references contain performance data to inform decisions:

| Reference | Contents |
|-----------|----------|
| `references/benchmarks.md` | Open rates, reply rates, conversion funnels by industry, multi-channel stats |
| `references/personalization.md` | Tiered personalization system, signal-to-noise rule, waterfall enrichment |
| `references/subject-lines.md` | Subject line data, question-based subjects, A/B testing, anti-pattern table |
| `references/follow-up-sequences.md` | 5-touch multichannel cadence, angle rotation, breakup emails, channel coordination |
| `references/frameworks.md` | All copywriting frameworks, reply rate techniques, LAER, contrarian/ polarizing CTAs, Spanish LAER |

Use this data to inform your writing — not as a checklist to satisfy.

---

## Related Skills

- **copywriting**: For landing pages and web copy
- **email-sequence**: For lifecycle/nurture email sequences (not cold outreach)
- **social-content**: For LinkedIn and social posts
- **product-marketing-context**: For establishing foundational positioning
