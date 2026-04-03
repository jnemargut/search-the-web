# /s — Search the Web From Your Coding Agent

A skill for AI coding agents that turns your terminal into a research assistant. Type a query like you'd type into a search engine, get back 3 synthesized mini-briefings with opinionated verdicts, ratings, and source links. No tab-switching. No 10 blue links. No leaving your flow.

```
/s best laptop under $1000
```

That's it. You're searching the web, from your coding agent, while you code.

---

## What It Looks Like

```
╭─────────────────────────────────────────────────────────────────╮
│ > /s best pizza apex nc                                         │
│                                                                 │
│ ### 1. Mezza Luna Pizzeria — Apex, NC                           │
│                                                                 │
│ Authentic NY pizza and Southern Italian cuisine that locals      │
│ consistently rank as Apex's best. Their Grandma Pie gets singled │
│ out repeatedly — "amazing crust, fresh sauce, perfect amount of  │
│ cheese" according to reviewers. Shows up on virtually every      │
│ "best of Apex" list.                                            │
│                                                                 │
│ Best for: NY pizza loyalists who want a real slice               │
│ Ratings: Quality 9/10 · Value 7/10 · Vibe 7/10                  │
│ Links: [Tripadvisor Review] · [Yelp Page]                       │
│ Sources: tripadvisor.com · yelp.com · pizzaware.com              │
│ ─────────────────────────────────────────────────────────────    │
│ ### 2. Frasketta Pizza Romana — Downtown Apex                    │
│                                                                 │
│ Roman-style pizza in a town full of NY slices. Limited hours     │
│ (Tue-Sat) signal a small-batch, quality-focused operation.       │
│ The Roman style sets it apart from everything else nearby.       │
│                                                                 │
│ Best for: Pizza nerds who want something different               │
│ Ratings: Quality 9/10 · Value 6/10 · Vibe 9/10                  │
│ Links: [Official Site] · [Tripadvisor Review]                    │
│ Sources: tripadvisor.com · yelp.com · fraskettapizza.com         │
│ ─────────────────────────────────────────────────────────────    │
│ ### 3. J & S New York Pizza — 804 Perry Rd                       │
│                                                                 │
│ The OG. Serving Apex since 1995. Family-owned with 30 years of  │
│ staying power. Not the fanciest, but reliable and loved.         │
│                                                                 │
│ Best for: Families who want dependable, no-frills NY pizza       │
│ Ratings: Quality 7/10 · Value 8/10 · Vibe 6/10                  │
│ Links: [Official Site] · [Yelp Page]                             │
│ Sources: jandsnypizza.com · yelp.com · tripadvisor.com           │
│ ─────────────────────────────────────────────────────────────    │
│ Searched 30+ sources across 3 searches.                          │
│ Say "more" for 3 more results, or refine: just tell me           │
│ what to change.                                                  │
╰─────────────────────────────────────────────────────────────────╯
```

Then just keep talking:

```
> but Neapolitan style
> more
> what about delivery options
```

It remembers your search and refines naturally.

---

## Why This Exists

You're deep in code. A thought pops into your head — "what's the best way to handle auth tokens?" or "where should I eat lunch?" or "what laptop should I buy?"

Normally you'd:
1. Switch to a browser
2. Type a query into a search engine
3. Click through 6-10 links
4. Read a bunch of SEO-optimized fluff
5. Mentally synthesize the answer yourself
6. Switch back to your code
7. Try to remember what you were doing

With `/s`, you:
1. Type `/s` and your query
2. Get 3 synthesized answers with verdicts and ratings
3. Keep coding

**It does what you'd do after a search — but skips the 20 minutes of clicking, reading, and comparing.** Like having a research assistant who reads 15 tabs so you don't have to.

---

## How It's Different

| | Traditional Search Engine | AI Answer Engine | `/s` |
|---|---|---|---|
| **Where it runs** | Browser (context switch) | Browser or separate app | Right in your terminal |
| **What you get** | 10 blue links to read yourself | 1 synthesized answer | 3 opinionated mini-briefings |
| **Source diversity** | One algorithm's ranking | One synthesis, few sources | Multi-angle (general + community + reviews) |
| **Verdicts** | None — you decide | Sometimes | Every result: "Best for: ..." |
| **Ratings** | None | None | Adaptive per query type |
| **Deep links** | Yes | Sometimes | Yes — to specific pages |
| **Refinement** | New search from scratch | Conversational | Conversational — "but cheaper" |
| **More results** | Page 2 (who goes there?) | Ask again | Say "more" for 3 fresh ones |
| **Context switch** | Yes — leave your editor | Yes — separate app | None — stay in your flow |

---

## What Makes the Results Better

The skill doesn't just run a single search. It:

1. **Classifies your intent** — is this a recommendation, a product comparison, a how-to, a factual question, or a local search?
2. **Searches from multiple angles** — general web, community discussions, and specialist review sites. Different angles for different intents.
3. **Deduplicates and synthesizes** — same result from 3 sources? Merged into one briefing with the best info from each.
4. **Adds judgment** — a "Best for" verdict on every result telling you *who* it's ideal for. Plus adaptive ratings that change based on what you're searching (Quality/Value/Vibe for restaurants, Performance/Build/Value for products, Clarity/Completeness for tutorials).
5. **Cites everything** — every result includes source links so you can verify.

---

## Install

### For Claude Code users

1. Clone this repo (or just grab the skill folder):

```bash
git clone https://github.com/jnemargut/search-the-web.git
```

2. Copy the skill into your global skills directory:

```bash
cp -r search-the-web/.claude/skills/s ~/.claude/skills/s
```

3. That's it. Open any project and type:

```
/s your query here
```

### For other AI coding agents

The core of this skill is a single markdown file: [`.claude/skills/s/SKILL.md`](.claude/skills/s/SKILL.md). It's a prompt that instructs an AI agent how to search, synthesize, and format results.

If your coding agent supports custom instructions or skills, you can adapt the SKILL.md to your agent's format. The key requirements are:
- The agent needs web search capability
- The agent needs to be able to run multiple searches in parallel
- The agent should output inline markdown

---

## Examples

**Local recommendations:**
```
/s best coffee shops downtown durham
/s things to do this weekend in austin
/s good running trails near me
```

**Products:**
```
/s best mechanical keyboard under $100
/s best laptop for video editing 2026
/s wireless earbuds with best battery life
```

**How-to:**
```
/s how to set up SSH keys on mac
/s how to fix a running toilet
/s how to negotiate a raise
```

**Factual:**
```
/s what is the capital of montana
/s when did the Berlin Wall fall
/s what's the current Fed interest rate
```

**Comparisons:**
```
/s react vs svelte for a new project
/s renting vs buying in a high interest rate market
/s postgres vs mysql for a small saas
```

**Random mid-coding thoughts:**
```
/s what's that design pattern where you wrap an object to add behavior
/s is daylight saving time this weekend
/s good team lunch spots near downtown raleigh
```

---

## The `/s` Philosophy

Two keystrokes. That's intentional.

If this skill is going to replace switching to a browser, it needs to be faster than switching to a browser. `/s` is to web search what `Cmd+K` is to a search bar — muscle memory, not a decision.

You don't type `/search-the-web-and-synthesize-results`. You type `/s`. Then your query. Then you're back to work.

---

## How Refinement Works

After getting results, just talk naturally:

```
/s best pizza near me
```
*[3 results appear]*

```
but Neapolitan style
```
*[3 new results, refined for Neapolitan]*

```
more
```
*[3 more results, numbered 4-6, no repeats]*

```
what about delivery options
```
*[3 new results focused on delivery]*

No special syntax. No re-typing your query. It remembers context and builds on it.

---

## Adaptive Ratings

Ratings change based on what you're searching for. The skill picks dimensions that actually help you decide:

| Query Type | Dimensions |
|---|---|
| Restaurants | Quality / Value / Vibe |
| Products | Performance / Build / Value |
| Services | Quality / Price / Reliability |
| Activities | Quality / Accessibility / Value |
| Tutorials | Clarity / Completeness |
| Factual | *(no ratings — just the answer)* |

Ratings use the full 1-10 range. A budget pick might get Value 9/10 but Quality 6/10. That's useful. If everything gets 8/10, ratings are worthless.

---

## License

MIT. Do whatever you want with it.
