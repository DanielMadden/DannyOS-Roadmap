# DatingOS

DatingOS is the dating discovery and relationship-intake layer of DannyOS. It is intended to reduce profile-review fatigue, repetitive swiping, messaging overhead, and context switching while directing attention toward the most compatible and promising candidates.

DatingOS should integrate with MessageOS for conversations and ContactOS for durable contact, interaction, and relationship history.

## Product outcome

Supported candidates from Tinder, Facebook Dating, Hinge, and future dating services should be reviewable through one structured workflow. The system should aggregate available profile information, calculate an explainable compatibility score, prioritize strong candidates, assist with conversation, and preserve meaningful interactions after a match progresses.

The compatibility model should estimate fit for the user’s stated goals. It should not claim to measure a person’s objective worth, predict consent, or determine whether a relationship will succeed.

## Candidate aggregation

- Present supported candidates from multiple platforms in one queue.
- Preserve the source platform and source profile identifier.
- Detect likely duplicates without merging records automatically.
- Normalize comparable profile fields while preserving original profile text and media references.
- Track candidate state, including new, reviewed, passed, interested, matched, active conversation, date planned, converted to ContactOS, paused, and closed.
- Keep platform-specific actions and limitations visible.

## Compatibility scoring

The scoring system may consider user-defined factors such as:

- Relationship goals
- Shared interests
- Values and priorities
- Lifestyle compatibility
- Communication preferences
- Location and travel distance
- Availability and scheduling compatibility
- Substance use and other practical preferences
- Desired relationship pace
- Explicit positive and negative criteria

Each criterion should have a configurable weight. The interface should show which information came directly from a profile, which information was inferred, which information is unknown, and how each factor affected the result.

The model should:

- Avoid treating missing information as a negative fact.
- Avoid inferring sensitive traits that were not explicitly provided.
- Separate dealbreakers from preferences.
- Display confidence based on the amount and quality of available information.
- Allow weights and criteria to change over time.
- Preserve score history so changes can be explained.
- Avoid optimizing solely for engagement, match volume, or time spent in the application.

## Review workflow

- Surface the highest-confidence compatible candidates first.
- Support focused review sessions with a configurable candidate limit.
- Provide concise summaries without hiding the original profile.
- Explain each recommendation and uncertainty.
- Allow quick interested, pass, save, and needs-more-information decisions.
- Support user-defined automatic exclusions only when the rule is explicit, reversible, and auditable.
- Avoid endless-scroll and variable-reward patterns that increase compulsive use.

## Matching and platform actions

DatingOS may propose platform actions such as like, pass, or priority review where supported. Consequential actions should be visible in an approval queue by default.

The system should:

- Show the candidate, destination platform, proposed action, and reason before execution.
- Record every executed action and failure.
- Prevent duplicate actions during retries.
- Allow automation rules to be disabled immediately.
- Respect platform rate limits and account restrictions.
- Avoid bypassing provider security or simulating unsupported clients in violation of provider terms.

## Conversation assistance

MessageOS should manage supported dating conversations after a match is established.

Capabilities should include:

- Summarize the profile and conversation history.
- Track unanswered questions, stated preferences, plans, and commitments.
- Suggest opening messages based on authentic shared context.
- Draft replies using the user’s intended meaning and preferred tone.
- Flag ambiguity or missing context rather than inventing personal facts.
- Show the final recipient, platform, and text before dispatch.
- Require approval before sending by default.
- Preserve unsent drafts and detect delivery failures.

AI assistance should reduce drafting effort without misrepresenting the user’s identity, intentions, experiences, or availability. The user remains responsible for messages sent through the account.

## ContactOS integration

A match may become a ContactOS record when the user chooses to preserve the connection or when a defined relationship threshold is reached and approved.

The transfer should include only approved information:

- Name and preferred identifier
- Dating platform and profile link or source identifier
- Available contact methods
- General location
- Relationship and dating status
- Confirmed interests and preferences
- Important dates and plans
- Approved conversation summary
- Boundaries and relevant notes

ContactOS should detect possible existing contacts before creating a new record.

## Date and interaction scoring

DatingOS uses the general ContactOS interaction model rather than a separate date-only scoring system.

Scorable interaction types include:

- Text conversations
- Phone calls
- Video calls or FaceTime
- Dates
- Hangouts
- Group activities
- Other meaningful interactions

Each score may include an optional explanation, activity, context, and relevant observations. ContactOS should calculate all-time and rolling 30-, 90-, and 180-day results overall and by interaction type.

A candidate’s pre-match compatibility score and post-interaction experience scores should remain separate. Profile compatibility is a prediction; interaction scoring is recorded experience.

## Neurodivergent interaction design

DatingOS should reduce the burdens associated with ADHD, OCD, autism, and overlapping needs.

- Limit the number of candidates shown in one review session.
- Preserve progress after interruption.
- Make reviewed, unresolved, and completed states explicit.
- Reduce notification pressure and repeated checking.
- Avoid engagement-oriented streaks, scarcity prompts, and swipe counters.
- Support adjustable information density and sensory intensity.
- Explain why a candidate or message requires attention.
- Provide a low-energy mode that reduces the number of decisions required.
- Separate uncertainty from confirmed incompatibility.
- Make it easy to pause dating activity without losing state.

## Privacy, consent, and safety

Dating data may include intimate, sensitive, and identifying information about multiple people. The private application data must never be committed to the public roadmap.

The implementation should:

- Encrypt profiles, messages, media references, notes, scores, and credentials.
- Use the minimum provider permissions necessary.
- Define retention and deletion rules for passed, unmatched, blocked, and inactive candidates.
- Prevent private profile or message data from entering unapproved model training.
- Avoid facial recognition or identity research outside information intentionally supplied through approved sources.
- Preserve block and report actions without overriding platform safety controls.
- Require explicit approval before sharing contact information, scheduling a date, or making a commitment.
- Keep compatibility scores and private notes inaccessible to candidates and other contacts.
- Maintain an audit trail of reads, recommendations, drafts, approvals, platform actions, and sends.

## Platform constraints

Dating platforms may restrict personal-account APIs, profile aggregation, automated swiping, message access, or third-party dispatch. Capabilities must be verified for each provider before implementation.

Each connector should be classified as:

- Full integration
- Limited integration
- Read-only integration
- Notification-assisted integration
- Manual import
- Unsupported

DatingOS should represent unsupported capabilities honestly rather than depend on fragile automation or claim complete synchronization.

## Initial delivery sequence

1. **Provider feasibility matrix** — verify candidate, match, message, and action capabilities for each target platform.
2. **Preference model** — define goals, weighted compatibility criteria, dealbreakers, uncertainty, and confidence.
3. **Manual candidate intake** — validate scoring and review behavior before connecting live accounts.
4. **Read-only aggregation** — connect the most capable provider without executing platform actions.
5. **Review queue** — add summaries, explanations, limits, and decision state.
6. **MessageOS integration** — add conversation summaries and editable drafts.
7. **Approval-based actions** — execute supported likes and replies with destination verification and audit history.
8. **ContactOS integration** — transfer approved matches and interaction history without duplication.
9. **Accessibility validation** — test ADHD-, OCD-, and autism-informed workflows before expanding automation.

## Open product decisions

- What relationship goals should the initial compatibility model support?
- Which criteria are dealbreakers, preferences, or informational only?
- Which traits should never be inferred?
- How should confidence change as more interactions occur?
- When should a match become a ContactOS record?
- Which candidate actions may be proposed, queued, or automated?
- Which message types, if any, may eventually be preapproved?
- How long should profiles, messages, scores, and media references be retained?
- How should the system behave when a dating platform is partially synchronized or unavailable?
- What defines a completed dating review session?
