# DannyOS — Roadmap

DannyOS is a connected personal operating system designed to support discovery, decision-making, planning, and follow-through across major areas of life.

This repository contains the public product roadmap. It documents intended outcomes first and adds technical detail as each feature reaches implementation readiness.

## Design mandate

DannyOS is intended to improve quality of life for neurodivergent users, including people with ADHD, OCD, and autism. The system should reduce fragmentation, memory burden, decision fatigue, context switching, notification overload, and the effort required to begin or complete routine actions.

The product should adapt to the user rather than require the user to conform to conventional productivity systems. Calm presentation, predictable behavior, explicit state, reversible actions, adjustable stimulation, and low-friction recovery are foundational requirements rather than optional accessibility features.

## Core platform

DannyOS is intended to operate across a shared platform layer:

- **Android** — the primary mobile control surface, selected for deeper operating-system integration and automation capabilities
- **Self-hosted storage** — the long-term system of record for files, photographs, exports, and application data
- **Local AI** — locally hosted language models for private or routine workloads that do not require paid model APIs
- **DannyOS dashboard** — the unified interface for status, history, predictions, recommendations, and approved controls
- **CalendarOS** — the planning and allocation layer for time, tasks, routines, commitments, recovery, and reflection
- **Notion** — an integrated knowledge and planning layer rather than the sole system of record
- **Google Calendar** — the initial external calendar provider and synchronization target
- **Gmail** — the source for confirmations, receipts, and follow-up signals

These capabilities are shared platform services rather than one-off connections rebuilt separately for every feature. See [Platform Direction](PLATFORM.md) for the initial architecture goals and open decisions.

## Development workflow

DannyOS uses a multi-model development workflow. Codex is the primary implementation environment for architecture, engineering, testing, documentation, and maintenance. Claude is the preferred design partner for UI/UX direction, interaction design, and visual critique. Repository artifacts remain the source of truth between tools.

See [Development Workflow](DEVELOPMENT-WORKFLOW.md) for role boundaries, handoff requirements, and the design-to-implementation process.

## Feature roadmap

### CalendarOS

**Goal:** Allocate time intentionally across commitments, tasks, relationships, health, maintenance, relaxation, and recovery while allowing the schedule to adapt when reality changes.

CalendarOS should give every hour an explicit purpose without treating every hour as work. The AI-assisted planner should coordinate tasks, deadlines, routines, energy, travel, personal priorities, and protected downtime.

Core capabilities include:

- Daily schedules developed collaboratively with AI.
- Weekly planning based on priorities, commitments, and realistic capacity.
- Sprint planning, sprint review, and daily scrum integration.
- Time-blocking for tasks, projects, routines, errands, relationships, health, hobbies, relaxation, and unstructured recovery.
- Dynamic rescheduling when tasks take longer, plans change, or energy is lower than expected.
- Clear separation between planned time, actual time, and completed outcomes.
- Buffers, transitions, breaks, and unscheduled capacity.
- Explanations and approval before consequential calendar changes.
- ADHD-, OCD-, and autism-informed scheduling that avoids shame, brittle plans, and over-optimization.

See [CalendarOS](CALENDAROS.md) for the initial planning model, operating ceremonies, scheduling rules, and delivery sequence.

### ConcertOS

**Goal:** Reduce missed concert opportunities and ensure that ticket purchases receive timely follow-through after interest is confirmed.

#### Build a taste profile

- Use the MusicOS taste profile and Spotify integration.
- Track artists already associated with listening activity.
- Prioritize metal, emo, EDM, indie, and indie rock.
- Allow the taste profile to evolve over time instead of relying on a permanent manual list.

#### Find concerts every morning

- Scan concert and artist sources daily for newly announced shows.
- Prioritize shows in Idaho.
- Include Utah when the artist or show is big enough to justify the drive.
- Avoid duplicate discoveries when multiple sources list the same show.

#### Build a concert decision queue

- Put new discoveries into a simple review list.
- Allow each concert to be marked as interested or not interested.
- Explore a Tinder-style swipe experience for quick decisions.
- Consider a dedicated phone app if that is the best interface.

#### Keep the calendar useful

- Create and maintain a dedicated concerts calendar.
- Add discovered concerts with artist, venue, city, date, source, and ticket link.
- Clearly distinguish potential concerts from confirmed attendance plans.
- Keep events updated if the date, venue, or status changes.

#### Support ticket purchasing

- Surface concerts that still require a decision or ticket purchase.
- Generate ticket-purchase reminders after interest is confirmed.
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

- What geographic area should qualify as local within Idaho?
- Which Utah cities are in range?
- What makes a Utah show “big enough” to surface?
- Which concert sources give the best coverage without overwhelming the system?
- Should discovered concerts be added to the calendar immediately or only after interest is confirmed?
- Is the first review experience a Notion view, a lightweight web app, or a native phone app?
- How should the system handle festivals, multi-day events, and multiple tour dates?

## Suggested delivery phases

1. **Taste profile** — MusicOS integration plus artist and genre signals.
2. **Daily discovery** — Idaho-first search, Utah fallback, and duplicate handling.
3. **Decision queue** — interested/not interested workflow.
4. **Concert calendar** — dedicated calendar and event lifecycle.
5. **Ticket follow-through** — reminders, on-sale dates, and purchase status.
6. **Gmail verification** — confirmation matching and reminder shutoff.
7. **Notion command center** — dashboard, history, and cross-feature visibility.
8. **Mobile experience** — swipe-based review if the earlier workflow proves useful.

### MusicOS

**Goal:** Build a provider-independent music intelligence and playlist-management system that understands listening behavior, lyrical themes, emotional context, and personal life patterns more deeply than a general streaming recommendation engine.

Spotify is the initial integration, but MusicOS should own the personal taste model, tags, playlist structure, and derived insights.

Core capabilities include:

- Aggregate listening history, saved music, artists, albums, genres, playlists, and behavioral signals.
- Maintain flexible tags for genres, subgenres, moods, emotions, themes, contexts, eras, and personal associations.
- Track licensed lyrics or lyric references and analyze themes without redistributing copyrighted text.
- Distinguish directly observed metadata from AI-inferred emotion, meaning, or mood.
- Organize inconsistent playlist names, folders, duplicates, sparse playlists, and abandoned collections.
- Provide advanced search, filtering, sorting, and conversational playlist management.
- Generate highly personalized playlists for activities, energy levels, emotional needs, seasons, events, relationships, and other life contexts.
- Preserve playlist history and require review before destructive reorganization.
- Supply the richer taste profile used by ConcertOS.

See [MusicOS](MUSICOS.md) for the initial data model, tagging system, lyric and emotion boundaries, playlist workflows, and delivery sequence.

### ContactOS

**Goal:** Provide one private, unified view of meaningful personal and professional relationships and support more intentional relationship maintenance.

ContactOS is the umbrella system for friends, family, acquaintances, work relationships, and other meaningful contacts. **FriendOS** is the component focused specifically on friendship maintenance.

#### Build one unified people directory

- Store every contact in one place across iOS, Android, and Windows.
- Track names, contact methods, birthdays, relationship type, location, and current life context.
- Distinguish local people from people who live elsewhere.
- Track the city or area someone is in without putting private location data in the public roadmap.
- Merge duplicate records without losing history.

#### Support friendship maintenance

- Identify relationships where too much time has passed since the last interaction.
- Adjust suggested contact frequency based on relationship context and recorded interaction quality.
- Provide birthday reminders early enough to support thoughtful planning rather than only last-minute messages.
- Keep a history of hangouts, calls, messages, and meaningful interactions.

#### Track how interactions actually feel

- Allow any meaningful interaction to receive a score from 1–10.
- Support interaction types including text conversations, dates, hangouts, phone calls, video calls, and other significant contact.
- Preserve an optional note explaining the score.
- Calculate an all-time average plus rolling 1-month, 3-month, and 6-month scores.
- Compare overall scores with scores for each interaction type.
- Show whether a relationship is improving, declining, or simply changing.
- Counteract unreliable memory about the quality and value of past interactions.

#### Calculate commonality

- Maintain a personal library of interest and compatibility tags.
- Give each tag a weight based on its personal importance.
- Add points for shared interests and valued qualities.
- Subtract points for negative compatibility tags, such as behaviors or traits experienced as draining.
- Support practical factors such as heavy drinking, smoking, or vaping.
- Keep these labels private, editable, and framed as subjective observations rather than objective judgments about another person.

#### Track personal relationship assessments

- Allow each person to receive a direct personal score from 1–10.
- Preserve an explanation for the selected score.
- Allow the score to be updated as the relationship changes.
- Keep a private score history that shows how the relationship has evolved.

#### Recognize pressure and imbalance

- Track relationship dynamics that create pressure, including situations where one person appears to be another person’s only friend or primary support system.
- Let those dynamics influence suggested boundaries and contact frequency.
- Surface relationships that feel one-sided, demanding, or consistently negative.
- Support decisions ranging from reaching out more often to keeping distance or intentionally ending contact.

#### Provide recommendations without automating consequential decisions

- Combine recency, interaction quality, commonality, personal assessment, relationship type, and pressure factors.
- Recommend contacts who may warrant outreach, more frequent interaction, less frequent interaction, or reassessment.
- Explain which signals caused a recommendation.
- Never automatically message someone, end a relationship, or make another consequential relationship decision.

#### Sync with DannyOS

- Use Notion as the private relationship dashboard and knowledge layer.
- Use Calendar for birthdays, planned hangouts, and appropriate reminders.
- Use Gmail only for explicitly approved signals and never expose private correspondence in the public roadmap.

See [ContactOS](CONTACTOS.md) for the initial product definition and scoring model.

### MessageOS

**Goal:** Consolidate supported messaging networks into one low-friction inbox that can scan, summarize, prioritize, draft, and dispatch replies while preserving user control.

MessageOS is intended to support Instagram, Snapchat, Facebook Messenger, Discord, Telegram, and additional messaging services where official platform capabilities permit reliable integration.

Core capabilities include:

- One inbox across connected messaging networks.
- Cross-network search and conversation history.
- AI-generated summaries and action extraction.
- Prioritization based on urgency, relationship, commitment, and recency.
- Reply drafting that preserves conversation context and user intent.
- Explicit approval before messages are dispatched by default.
- Dispatch back through the original network from one application.
- ADHD-, OCD-, and autism-informed presentation and interaction design.
- Clear handling of unavailable, limited, or read-only platform integrations.

See [MessageOS](MESSAGEOS.md) for the initial product definition, safety model, and accessibility requirements.

### DatingOS

**Goal:** Reduce the time and cognitive load required to review dating candidates while concentrating attention on the most compatible and promising connections.

DatingOS is intended to aggregate supported candidates and conversations from Tinder, Facebook Dating, Hinge, and future dating services. It should apply an explainable compatibility model, organize review queues, assist with messages, and preserve dating interactions in ContactOS.

Core capabilities include:

- One candidate queue across supported dating platforms.
- Compatibility scoring based on user-defined preferences, values, interests, lifestyle, relationship goals, and practical constraints.
- Explanations for each score and recommendation.
- High-confidence review queues that reduce repetitive profile screening.
- Conversation summaries and context-aware message drafting through MessageOS.
- Approval-based dispatch and clear attribution of every action to its destination platform.
- Conversion of relevant matches into ContactOS records without creating duplicates.
- Interaction scoring for texts, calls, video calls, dates, and other meaningful contact.
- ADHD-, OCD-, and autism-informed review flows that minimize swiping fatigue, uncertainty, and context switching.

See [DatingOS](DATINGOS.md) for the initial product definition, scoring boundaries, integration model, and delivery sequence.

## Historical idea backlog

Earlier Life OS and personal-system documents contain additional product concepts that have not yet been validated or promoted into the active roadmap. These ideas are preserved in [Historical Ideas](HISTORICAL-IDEAS.md) for future review.

## Status

This roadmap is intentionally early. The desired experience is documented; implementation choices, data sources, privacy boundaries, and exact location rules still need to be defined before feature work begins.
