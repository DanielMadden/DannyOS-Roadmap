# MessageOS

MessageOS is the unified communications layer of DannyOS. It is intended to reduce the fragmentation created by separate social and messaging applications while making it easier to understand, prioritize, and complete communication.

## Product outcome

Supported conversations from Instagram, Snapchat, Facebook Messenger, Discord, Telegram, and future networks should be accessible through one application. The system should scan approved conversations, summarize relevant context, identify required actions, draft replies, and dispatch approved responses through the original network.

The system should create a communication environment that works with neurodivergent attention, memory, sensory, and executive-function needs rather than increasing cognitive load.

## Unified inbox

- Combine supported direct messages, group messages, and selected channels into one queue.
- Preserve the source network and original conversation identity.
- Support unified search across people, messages, dates, attachments, commitments, and topics.
- Merge known identities across networks without merging conversations incorrectly.
- Allow network, relationship, urgency, and message-type filters.
- Preserve unread state without allowing unread counts to dominate the interface.
- Distinguish messages that require action from messages that are informational or complete.

## Scanning and summarization

- Scan only accounts, conversations, and time ranges explicitly approved by the user.
- Summarize long conversations and activity since the last review.
- Extract questions, commitments, invitations, dates, decisions, and follow-up items.
- Identify potentially time-sensitive messages without representing predictions as facts.
- Show the underlying messages that support each summary or extracted action.
- Allow summaries to be corrected when context is misunderstood.

## Prioritization

MessageOS should prioritize messages using transparent signals such as:

- Explicit deadlines or dates
- Direct questions
- Existing commitments
- Relationship importance
- Time since receipt
- Time since the last response
- Conversation sensitivity
- Whether the sender is waiting on a decision

Priority should remain adjustable. The system should not equate message volume, emotional tone, or repeated follow-ups with legitimate importance by default.

## Reply drafting and dispatch

- Draft replies using the relevant conversation context and the user’s stated intent.
- Allow tone, length, directness, and level of detail to be adjusted.
- Preserve drafts across devices.
- Show the destination network, recipient, and final text before dispatch.
- Require explicit approval before sending by default.
- Record when and where a message was dispatched.
- Detect delivery failures and preserve the unsent draft.
- Prevent duplicate sends during retries or synchronization conflicts.

Future narrowly scoped automations may support preapproved low-risk responses, but open-ended autonomous messaging should not be the default.

## Neurodivergent interaction design

MessageOS should be designed for users with ADHD, OCD, autism, and overlapping needs.

### Reduce attention fragmentation

- Replace multiple network inboxes with one processing queue.
- Support focused review sessions with configurable limits.
- Hide nonessential counters, animations, recommendations, and engagement features.
- Preserve context when switching between conversations or devices.
- Make the next useful action obvious without forcing immediate action.

### Reduce uncertainty and compulsive checking

- Display synchronization time and completeness clearly.
- Confirm whether a message was sent, delivered, failed, or remains a draft.
- Avoid ambiguous badges and state changes.
- Provide a reliable completed state for inbox-processing sessions.
- Allow notifications and refresh frequency to be intentionally bounded.

### Support autistic communication needs

- Preserve full context and conversation history.
- Explain why a message was prioritized or summarized in a particular way.
- Offer structured reply modes such as direct, warm, concise, boundary-setting, or clarification-seeking.
- Avoid automatically inferring intent, emotion, or social meaning as fact.
- Allow sensory intensity, information density, layout, and motion to be adjusted.

### Support recovery

- Make postponed conversations easy to find again.
- Preserve unsent work automatically.
- Provide reminders without punishment, shame, or escalating visual pressure.
- Allow an interrupted inbox session to resume from the same position.
- Support a low-energy mode that reduces the number of decisions required.

## Platform integration constraints

Messaging capabilities vary substantially by provider. Some platforms offer official APIs for bots, business accounts, or limited message types but do not permit complete personal-inbox access or third-party dispatch.

Each connector should document:

- Whether reading personal messages is supported.
- Whether historical synchronization is supported.
- Whether sending replies is supported.
- Which account types are eligible.
- Rate limits, review requirements, and data-retention rules.
- Whether the connector is full access, limited access, notification-assisted, or read-only.

MessageOS should not bypass platform security, impersonate unsupported clients, or depend on fragile automation that violates provider terms. Unsupported networks should degrade honestly rather than appear fully synchronized.

## Privacy and security

Messages may contain sensitive information about the user and other people. The private application data must never be stored in the public roadmap.

The implementation should:

- Encrypt credentials, messages, drafts, summaries, and attachments.
- Use the minimum provider permissions necessary.
- Separate connector credentials from application data.
- Support provider disconnection and deletion of synchronized data.
- Define retention periods for message bodies, attachments, embeddings, and summaries.
- Prevent private messages from entering general-purpose model training or unapproved hosted services.
- Maintain an audit trail of reads, drafts, approvals, sends, failures, and automated actions.
- Support local processing when privacy or provider rules require it.

## Connections to other DannyOS modules

- **ContactOS:** resolve identities, relationship context, birthdays, boundaries, and desired contact frequency.
- **Calendar:** propose events and reminders from confirmed plans or commitments.
- **Task system:** convert approved commitments and follow-ups into actionable work.
- **Memory system:** preserve approved summaries and decisions without retaining unnecessary message content.
- **Dashboard:** show communication workload, unresolved commitments, connector health, and replies awaiting approval.

## Initial delivery sequence

1. **Provider feasibility matrix** — document the supported read, history, and send capabilities for each target network.
2. **Read-only aggregation** — connect the most capable provider and validate synchronization, identity, and privacy controls.
3. **Unified review queue** — add message state, filtering, prioritization, and completion behavior.
4. **Summaries and extraction** — generate cited summaries, questions, commitments, and dates.
5. **Draft workspace** — create editable replies without dispatch.
6. **Approval-based sending** — dispatch through supported providers with recipient verification and audit history.
7. **ContactOS integration** — connect identity and relationship context.
8. **Accessibility validation** — test the experience with ADHD-, OCD-, and autism-informed workflows before expanding automation.

## Open product decisions

- Which provider should be used for the first complete integration?
- Which accounts are personal, professional, community, or automated?
- Which conversations should be excluded from scanning?
- How long should raw messages, attachments, summaries, and embeddings be retained?
- Should conversation state remain provider-specific or be normalized across networks?
- What defines inbox completion?
- Which messages may create proposed tasks or calendar events?
- Which reply types, if any, may eventually be preapproved for automatic dispatch?
- How should MessageOS behave when a provider is unavailable, delayed, or only partially synchronized?
