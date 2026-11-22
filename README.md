# Danny OS — Roadmap

Danny OS is the operating system for my life: one connected system that helps me discover what matters, decide what I want to do, and actually follow through.

This repository is the public roadmap. It starts with the outcomes I want and will get more technical as each feature becomes ready to build.

## Core platform

Every Danny OS feature should be able to connect with:

- **Notion** — the long-term home for information, decisions, and dashboards
- **Google Calendar** — the source of truth for time, plans, and reminders
- **Gmail** — the source for confirmations, receipts, and follow-up signals

These are shared platform integrations, not one-off connections rebuilt separately for every feature.

## Feature roadmap

### Concert OS

**Goal:** Make it nearly impossible for me to miss a concert I would love—or forget to buy the ticket after deciding I want to go.

#### Discover my taste

- Connect Spotify.
- Track artists I already like.
- Track the genres I care about most: metal, emo, EDM, indie, and indie rock.
- Let my taste change over time instead of relying on a permanent manual list.

#### Find concerts every morning

- Scan concert and artist sources daily for newly announced shows.
- Prioritize shows in Idaho.
- Include Utah when the artist or show is big enough to justify the drive.
- Avoid duplicate discoveries when multiple sources list the same show.

#### Build a concert decision queue

- Put new discoveries into a simple review list.
- Let me mark each concert as interested or not interested.
- Explore a Tinder-style swipe experience for quick decisions.
- Consider a dedicated phone app if that is the best interface.

#### Keep the calendar useful

- Create and maintain a dedicated concerts calendar.
- Add discovered concerts with artist, venue, city, date, source, and ticket link.
- Clearly distinguish possibilities from concerts I am committed to attending.
- Keep events updated if the date, venue, or status changes.

#### Help me buy the ticket

- Show me the concerts that still need a decision or ticket purchase.
- If I say I am interested, remind me to buy tickets.
- Track presales, on-sale dates, deadlines, and price information when available.
- Stop purchase reminders after a ticket is confirmed.

#### Verify purchases through Gmail

- Detect ticket confirmations and receipts in Gmail.
- Match the confirmation to the correct concert.
- Mark the concert as ticket purchased.
- Store the useful confirmation details without exposing private email content publicly.

#### Sync with Notion

- Maintain a useful concert database and dashboard in Notion.
- Track discovery, interest, ticket, and attendance status.
- Preserve notes, links, and history for each concert.

## Open product decisions

- What exactly counts as “my area” in Idaho?
- Which Utah cities are in range?
- What makes a Utah show “big enough” to surface?
- Which concert sources give the best coverage without overwhelming the system?
- Should discovered concerts go directly onto the calendar or wait until I mark them interested?
- Is the first review experience a Notion view, a lightweight web app, or a native phone app?
- How should the system handle festivals, multi-day events, and multiple tour dates?

## Suggested delivery phases

1. **Taste profile** — Spotify connection plus artist and genre signals.
2. **Daily discovery** — Idaho-first search, Utah fallback, and duplicate handling.
3. **Decision queue** — interested/not interested workflow.
4. **Concert calendar** — dedicated calendar and event lifecycle.
5. **Ticket follow-through** — reminders, on-sale dates, and purchase status.
6. **Gmail verification** — confirmation matching and reminder shutoff.
7. **Notion command center** — dashboard, history, and cross-feature visibility.
8. **Mobile experience** — swipe-based review if the earlier workflow proves useful.

### Contact OS

**Goal:** Give me one private, unified view of every meaningful person I have interacted with—and help me invest in the relationships that actually make my life better.

Contact OS is the umbrella. It includes friends, family, acquaintances, work relationships, and other people in my life. **Friend OS** is the part focused specifically on maintaining friendships.

#### Build one unified people directory

- Store every contact in one place across iOS, Android, and Windows.
- Track names, contact methods, birthdays, relationship type, location, and current life context.
- Distinguish local people from people who live elsewhere.
- Track the city or area someone is in without putting private location data in the public roadmap.
- Merge duplicate records without losing history.

#### Help me maintain friendships

- Remind me when it has been too long since I reached out or spent time with someone.
- Adjust the suggested contact frequency based on the relationship and my actual experience with that person.
- Remind me about birthdays early enough to do something thoughtful—not just send a last-minute message.
- Keep a history of hangouts, calls, messages, and meaningful interactions.

#### Track how interactions actually feel

- Let me score each hangout or meaningful interaction from 1–10.
- Preserve a note explaining the score when I want one.
- Calculate an all-time average plus rolling 1-month, 3-month, and 6-month scores.
- Show whether a relationship is improving, declining, or simply changing.
- Help correct for the fact that I sometimes forget how much I enjoy spending time with someone.

#### Calculate commonality

- Maintain a personal library of interest and compatibility tags.
- Give each tag a weight based on how important that quality is to me.
- Add points when someone shares interests or qualities I value.
- Subtract points for negative compatibility tags, such as behaviors or traits I find draining.
- Support practical factors such as heavy drinking, smoking, or vaping.
- Keep these labels private, editable, and grounded in my own experience—not presented as objective judgments about a person.

#### Track my personal relationship assessment

- Let me give someone a direct personal score from 1–10.
- Let me explain why I chose that score.
- Allow me to update it whenever my view changes.
- Keep a private score history so I can see how the relationship has evolved.

#### Recognize pressure and imbalance

- Track relationship dynamics that create pressure, including feeling like I am someone’s only friend or primary support system.
- Let those dynamics influence suggested boundaries and contact frequency.
- Surface relationships that feel one-sided, demanding, or consistently negative.
- Support decisions ranging from reaching out more often to keeping distance or intentionally ending contact.

#### Make recommendations without making the decision for me

- Combine recency, interaction quality, commonality, personal assessment, relationship type, and pressure factors.
- Recommend who I may want to contact, see more often, see less often, or reassess.
- Explain which signals caused a recommendation.
- Never automatically message someone, cut ties, or make a consequential relationship decision for me.

#### Sync with Danny OS

- Use Notion as the private relationship dashboard and knowledge layer.
- Use Calendar for birthdays, planned hangouts, and appropriate reminders.
- Use Gmail only for explicitly approved signals and never expose private correspondence in the public roadmap.

See [Contact OS](CONTACT-OS.md) for the initial product definition and scoring model.

## Status

This roadmap is intentionally early. The desired experience is documented; implementation choices, data sources, privacy boundaries, and exact location rules still need to be defined before feature work begins.
