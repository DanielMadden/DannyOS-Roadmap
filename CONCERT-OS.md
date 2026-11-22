# Concert OS

Concert OS is the first feature in the Danny OS roadmap.

## User story

As someone who loves metal, emo, EDM, indie, and indie rock, I want a system that understands my Spotify taste, checks every morning for relevant concerts in Idaho and major shows in Utah, helps me quickly decide which ones I care about, puts them on a dedicated calendar, reminds me to buy tickets, and confirms purchases through Gmail so I do not miss shows or leave tickets sitting on my mental to-do list.

## Definition-readiness checklist

- [ ] Define the primary Idaho radius or list of cities.
- [ ] Define the acceptable Utah cities and driving threshold.
- [ ] Define the “big enough for Utah” rule.
- [ ] Choose initial concert data sources.
- [ ] Decide whether discovery creates a calendar event immediately.
- [ ] Define the states for discovered, interested, rejected, ticket needed, purchased, attended, canceled, and missed.
- [ ] Define what Gmail data may be read and what may be stored.
- [ ] Define the Notion database schema.
- [ ] Choose the first decision-queue interface.
- [ ] Define reminder timing and escalation rules.

## Privacy boundary

The public roadmap can describe behavior and architecture, but it must never contain OAuth credentials, tokens, private email content, ticket barcodes, payment details, private calendar data, or exact personal-location data.
