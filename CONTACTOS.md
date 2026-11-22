# ContactOS

ContactOS is the people layer of DannyOS. FriendOS lives inside it.

## Intent

I am not naturally good at maintaining friendships. I forget to reach out, and I sometimes forget how much I enjoy spending time with someone. I can also keep spending time with people I do not enjoy simply because the pattern already exists.

ContactOS should give me better memory and better signals. It should help me decide where to invest my time without pretending that a score can define a human being or make the decision for me.

## People in scope

- Friends
- Family
- Acquaintances
- Work relationships
- Formerly close relationships
- Anyone else I have meaningfully interacted with and may want to remember

Each person can have a relationship type, closeness level, local/remote status, city or general area, contact information, birthday, important context, and interaction history.

## Proposed scoring model

The model should keep its components separate. A single total can be useful for sorting, but I should always be able to see *why* someone received that result.

### 1. Interaction score

After a hangout or meaningful interaction, I can give the experience a score from 1–10 and optionally record why.

The system calculates:

- All-time average
- Rolling 30-day average
- Rolling 90-day average
- Rolling 180-day average
- Recent trend
- Number of scored interactions in each window

The number of interactions matters. A 10 based on one hangout should not look as certain as a 9 based on twenty hangouts.

### 2. Commonality score

I maintain a tag library. Each tag has:

- A name
- A positive or negative direction
- A weight showing how much it matters to me
- An optional category, such as interests, values, lifestyle, personality, or relationship dynamics
- An optional note explaining what the tag means to me

A person’s commonality score is the sum of their weighted tags. Positive shared interests and valued qualities add points. Negative compatibility factors subtract points.

Example positive tags might include metal, EDM, gaming, travel, deep conversations, creativity, ambition, or local adventures. Example negative tags might include shallow interactions, behavior I find annoying, heavy drinking, smoking, vaping, or a relationship dynamic that creates too much pressure.

Tags are private personal observations. They are not diagnoses, objective measures of intelligence or worth, or information to share with the person being scored.

### 3. Personal score

I can give each person a direct 1–10 personal score and explain the reason. This captures my own judgment when the calculated signals do not tell the whole story.

The system keeps the current score and a private history of previous scores, reasons, and dates.

### 4. Pressure and boundary signals

Some relationships create more responsibility than I want. For example, feeling like I am someone’s only friend or entire support system creates pressure and may mean I should keep more distance.

These should be explicit private signals, not hidden assumptions. They can reduce recommended contact frequency or trigger a suggestion to reassess boundaries.

### 5. Contact recommendation

A future recommendation model may consider:

- Time since last meaningful contact
- Desired contact frequency
- Relationship type
- Whether the person is local
- Interaction score and trend
- Commonality score
- Personal score
- Pressure or boundary signals
- Upcoming birthday or important event
- Existing plans already on the calendar

The output should be an explainable suggestion such as:

- Reach out soon
- Plan something
- Maintain the current rhythm
- Give this relationship more space
- Reassess the relationship
- Consider intentionally ending contact

No single low score should automatically produce a major recommendation. Recent scores should be shown with context, and the final choice always stays with me.

## Birthday and reminder system

- Store birthdays and the person’s preferred contact method.
- Remind me in advance when a gift, card, or plan may be appropriate.
- Remind me again on the birthday.
- Let me mark the acknowledgment complete.
- Avoid repeatedly nagging me once I have acted.

## Unified contacts

ContactOS should eventually become the private source of truth across iOS, Android, and Windows while syncing safely with the platforms I use.

The first version should focus on importing, matching, and deduplicating contacts rather than immediately replacing native contact systems. It should preserve source identifiers so sync can be reversible and auditable.

## Privacy and safety boundary

ContactOS contains sensitive information about real people. The application data must be private even if this roadmap is public.

The public repository must never contain:

- Contact details
- Birth dates tied to identifiable people
- Private notes or interaction histories
- Personal scores or tags
- Email or message content
- Precise locations
- Inferences presented as facts about another person
- Authentication credentials or provider tokens

Access should be encrypted, permissioned, exportable, and deletable. Integrations should use the minimum data necessary, and any automated message or consequential action should require my approval.

## Definition-readiness checklist

- [ ] Confirm whether ContactOS remains the umbrella with FriendOS inside it.
- [ ] Define relationship types and whether one person can have more than one.
- [ ] Define the interaction types that can receive scores.
- [ ] Decide how the overall score is calculated—or whether sorting by separate scores is better.
- [ ] Define how much recent interactions outweigh older ones.
- [ ] Define confidence rules for people with very few scored interactions.
- [ ] Build the initial positive and negative tag library and weights.
- [ ] Define contact-frequency options and reminder behavior.
- [ ] Define birthday reminder timing.
- [ ] Choose the first contact sources to import.
- [ ] Define duplicate-matching and conflict-resolution rules.
- [ ] Define what information belongs in Notion versus a more private encrypted data store.
- [ ] Define consent, retention, export, deletion, and account-recovery rules.
