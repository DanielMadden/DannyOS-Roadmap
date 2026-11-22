# MediaOS

MediaOS is the visual-media tracking, rating, review, organization, and discovery layer of DannyOS. It provides one unified place for movies, television series, anime, documentaries, specials, short films, and other watched video media.

Letterboxd and AniList are the initial external integrations. MusicOS remains a separate module for music and audio intelligence.

## Product outcome

MediaOS should preserve what has been watched, what is currently in progress, what should be watched next, how each work was experienced, and how preferences change over time. It should provide a consistent personal system even when external services use different media types, identifiers, rating scales, list structures, and progress models.

The system should answer:

- What has been watched, when, and how many times?
- Which series, seasons, or episodes are currently in progress?
- What was the rating and why?
- Which works are consistently liked or disliked?
- Which themes, genres, creators, studios, characters, and emotional qualities recur?
- What should be watched next for a particular mood, available time, person, or context?
- Which provider contains the authoritative or most recent record?

## Unified media catalog

Each work should have a canonical MediaOS record with provider-specific identifiers attached.

Supported media types should include:

- Movie
- Television series
- Television season
- Television episode
- Anime series
- Anime season or cour
- Anime episode
- OVA, ONA, or special
- Documentary
- Short film
- Miniseries
- Other visual media

The catalog should preserve titles, alternate titles, original language, release dates, runtime, episode counts, genres, creators, cast, studios, production companies, source material, artwork references, and provider links when available.

Duplicate detection should account for alternate titles, regional releases, remakes, adaptations, compilations, recaps, and works appearing in more than one provider catalog.

## Viewing state and history

MediaOS should support states such as:

- Not started
- Planning to watch
- In progress
- Paused
- Completed
- Abandoned
- Rewatching
- Archived

Viewing history may include:

- Start and completion dates
- Episode and season progress
- Individual viewing sessions
- Rewatch count
- Playback location or service when useful
- People present
- Watch context
- Progress corrections
- Reason for pausing or abandoning when recorded

History should preserve previous states rather than only the current status.

## Rating and scoring system

MediaOS should maintain a canonical personal score that can be translated to provider-specific rating scales without losing precision.

The default model may include:

- Overall score
- Enjoyment
- Story or writing
- Characters
- Visual direction or animation
- Performance or voice acting
- Music and sound
- Emotional impact
- Rewatch interest

Category scores should be optional and configurable. A quick overall rating should remain possible when detailed scoring would create unnecessary friction.

The system should:

- Record the date and version of each rating.
- Preserve rating changes over time.
- Distinguish a first-watch rating from later rewatches.
- Normalize Letterboxd, AniList, and future provider scales.
- Avoid pretending that scores from different scales are perfectly equivalent.
- Keep personal enjoyment separate from claims of objective quality.
- Allow unrated completion.

## Reviews and notes

Each work may have:

- A full written review
- A short reaction
- Private notes
- Public and private versions
- Spoiler and non-spoiler sections
- Favorite scenes, characters, episodes, or quotes
- Questions or themes for later reflection
- Rewatch notes
- Review revision history

AI may help organize, summarize, edit, or compare the user’s notes, but it should not fabricate opinions or publish a review without approval.

Copyrighted scripts, subtitles, or long quotations should not be copied into the public repository or redistributed without appropriate rights.

## Tags and analysis

MediaOS should support manual, provider-supplied, and AI-generated tags.

Tag categories may include:

- Genre and subgenre
- Tone
- Mood and emotion
- Themes
- Narrative structure
- Setting and time period
- Visual style
- Animation style
- Pacing
- Content sensitivities
- Relationship dynamics
- Character archetypes
- Studio, director, writer, or creator
- Source material
- Viewing context
- Personal association

Every inferred tag should record its source and confidence. User corrections should override automated analysis.

## Lists and organization

MediaOS should unify external lists without erasing their source or purpose.

Capabilities should include:

- Unified watchlist
- Provider-specific watchlists
- Custom ranked and unranked lists
- Favorites
- Seasonal anime queues
- Franchises and viewing order
- Director, studio, creator, and actor collections
- Mood, genre, theme, and context lists
- Shared lists for specific friends or groups
- Archived lists
- Advanced filtering and sorting

List changes should be reviewable and reversible where provider capabilities permit.

## Personalized discovery

Recommendations should use explicit ratings and broader context rather than provider engagement goals alone.

Potential inputs include:

- Rating history
- Review language
- Completion and abandonment behavior
- Rewatches
- Favorite genres, themes, creators, studios, and performers
- Available viewing time
- Desired emotional tone
- Current energy and attention capacity
- People watching together
- Calendar context
- Recent saturation with similar media
- Desired familiarity versus discovery

Every recommendation should explain the strongest reasons, uncertainties, and relevant constraints.

MediaOS should support bounded recommendation sessions rather than endless discovery feeds.

## Letterboxd integration

Letterboxd is the initial movie-oriented integration.

Desired synchronization includes, where supported:

- Watched films
- Diary entries and dates
- Ratings
- Reviews
- Likes
- Watchlist
- Lists
- Rewatches
- Provider identifiers or stable matching fields

Import, export, and write capabilities must be verified before implementation. Unsupported actions should be represented honestly rather than approximated through fragile automation.

## AniList integration

AniList is the initial anime-oriented integration.

Desired synchronization includes, where supported:

- Anime library
- Current status
- Episode progress
- Start and completion dates
- Scores
- Rewatches
- Notes
- Custom lists
- Favorites
- Provider identifiers

MediaOS should preserve anime-specific structures such as cours, OVAs, ONAs, specials, recaps, adaptations, source material, studios, and alternate titles.

## Synchronization and conflicts

Each synchronized field should define:

- Source provider
- Last successful synchronization
- Read and write support
- Authoritative system
- Conflict-resolution rule
- Local changes awaiting dispatch
- Provider changes awaiting review

MediaOS should avoid overwriting a more detailed local review, higher-precision score, or corrected record with a less expressive provider value.

## Neurodivergent interaction design

MediaOS should support ADHD, OCD, autism, and overlapping needs.

- Reduce choice overload with bounded recommendation sets.
- Make watch state and episode progress explicit.
- Preserve the exact point where list review or rating work was interrupted.
- Allow quick ratings without requiring detailed reviews.
- Support later review expansion without losing the original reaction.
- Avoid streaks, urgency prompts, endless feeds, and engagement pressure.
- Distinguish incomplete data from unfinished obligations.
- Provide adjustable information density and visual intensity.
- Support a low-energy mode for selecting something to watch with minimal decisions.
- Provide a clear completed state for list maintenance and review sessions.

## DannyOS integrations

- **CalendarOS:** reserve intentional viewing time and suggest works that fit the available block.
- **ContactOS:** preserve approved shared interests, recommendations, and group-viewing history.
- **DatingOS:** support approved shared media interests and date-night lists.
- **MusicOS:** connect soundtracks, scores, theme songs, artists, and related listening.
- **MessageOS:** extract approved recommendations or viewing plans from conversations.
- **Dashboard:** present current progress, unfinished series, recent ratings, and bounded recommendations.
- **Local AI:** analyze approved metadata, notes, and reviews locally when practical.

## Privacy and control

Viewing history, reviews, emotional tags, and person associations may reveal sensitive preferences or relationships. The implementation should:

- Encrypt credentials, private notes, history, and associations.
- Use minimum provider permissions.
- Distinguish public reviews from private notes.
- Require approval before publishing reviews, ratings, lists, or activity.
- Allow categories of data to remain local.
- Support correction, export, provider disconnection, and deletion.
- Maintain an audit trail of imports, synchronization, score changes, review publication, and list changes.
- Keep private viewing data out of the public roadmap.

## Initial delivery sequence

1. **Provider inventory** — document Letterboxd and AniList export, import, read, and write capabilities.
2. **Canonical catalog model** — define media types, identifiers, duplicate handling, and provider mappings.
3. **Read-only imports** — import available history, ratings, progress, reviews, and lists.
4. **Conflict report** — identify duplicate works, mismatched scores, and inconsistent status.
5. **Unified library** — present movies, shows, and anime through one searchable catalog.
6. **Rating and review model** — add canonical scores, history, notes, and spoiler controls.
7. **Approved synchronization** — write supported changes back to providers with an audit trail.
8. **Personalized discovery** — create bounded, explainable recommendations.
9. **DannyOS integrations** — connect CalendarOS, ContactOS, DatingOS, MusicOS, MessageOS, and the dashboard.
10. **Accessibility validation** — test choice load, progress clarity, interruption recovery, and low-energy workflows.

## Open product decisions

- Which scale should be the canonical MediaOS rating scale?
- Which category scores should be available by default?
- How should movie, episode, season, and series ratings relate?
- When should a partially watched work count as watched?
- How should abandoned works affect recommendations?
- Which system is authoritative when Letterboxd, AniList, and MediaOS disagree?
- Which reviews and lists are public, private, or selectively shared?
- How should anime entries be matched across alternate titles and release structures?
- Which metadata provider should supplement Letterboxd and AniList?
- How much broader DannyOS context should influence recommendations?
