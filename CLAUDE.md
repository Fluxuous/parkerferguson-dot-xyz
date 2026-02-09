# parkerferguson.xyz — Project Instructions

## Copy & Voice Rules

**All copy written for this site MUST be sanitized for AI tells before committing.** This is a hard rule, not a suggestion.

### Things to eliminate:
- Excessive em-dashes (one per paragraph max — they're an AI fingerprint when overused)
- "Delve," "tapestry," "landscape," "leverage," "utilize," "facilitate," "comprehensive"
- "In today's [anything]," "it's worth noting," "at the end of the day"
- Parallel structure in lists of three ("X, Y, and Z" repeated across paragraphs)
- Starting consecutive sentences with "I"
- Overly balanced sentence pairs (thesis-antithesis patterns)
- Filler transitions: "That said," "Moreover," "Furthermore," "Additionally"
- Vague superlatives: "incredibly," "remarkable," "fascinating," "compelling"
- Any sentence that sounds like a LinkedIn post
- Any sentence where you could swap in anyone's name and it would still work

### What good copy sounds like here:
- Short sentences mixed with long ones. Irregular rhythm.
- Specific details over abstract claims
- Active voice, plain language
- The way someone talks when they're excited about something and explaining it to a friend
- Comfortable with fragments. And starting sentences with conjunctions.
- Doesn't over-explain. Trusts the reader.

### Tone (codified from docs/IDEAS.md):
- Optimistic, forward-looking, energized
- Confident without being a douchebag
- This site IS the higher self — it doesn't describe the pursuit of it
- No apology, no hedging, no confessional shame
- Inspiring, not performative

## Tech Stack
- Astro v5 + Tailwind CSS v3 + MDX
- Content collections with Zod schemas (blog, projects, links)
- Deployed to Vercel via `vercel --prod` (GitHub auto-deploy not yet connected)
- Fonts: Lora (headings), Inter (body), JetBrains Mono (code)

## Deployment
Push to GitHub, then run `vercel --prod --yes` to deploy.
GitHub auto-deploy is not wired up yet — it requires connecting the repo in the Vercel dashboard.
