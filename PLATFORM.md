# DannyOS Platform Direction

DannyOS is intended to become a unified, AI-assisted control layer for personal information, planning, communication, automation, and decision support. The platform should track relevant state, preserve history, identify patterns, produce explainable predictions, and provide controlled ways to take action.

The platform is specifically intended to reduce the executive-function, attention, memory, sensory, and context-switching burdens experienced by neurodivergent users, including people with ADHD, OCD, and autism.

This document defines the desired platform direction. It does not commit the roadmap to a specific device, hosting provider, model, or application framework.

## Android-first mobile strategy

Android is the preferred long-term mobile platform because it permits deeper integration with applications, notifications, background services, intents, files, and operating-system automation than is generally available on iPhone.

The Android experience should:

- Serve as the primary mobile interface for DannyOS.
- Provide fast access to the dashboard, assistants, tasks, contacts, files, and current recommendations.
- Receive and process explicitly approved notification signals.
- Support share-sheet and intent-based capture from other applications.
- Run appropriate background synchronization and reminder workflows.
- Expose clear controls for every operating-system permission.
- Avoid broad accessibility, notification, microphone, or file permissions unless a defined feature requires them.
- Remain useful during temporary loss of connectivity.

Migration from iPhone should be staged. Core contacts, files, photographs, calendars, messages, authentication methods, and recovery options should be verified before Android becomes the primary device.

## Self-hosted files and photographs

DannyOS should reduce dependence on Google Drive, Apple Photos, and other provider-controlled storage by maintaining an independently controlled storage system.

The storage layer should support:

- General file hosting and folder organization.
- Original-quality photograph and video storage.
- Mobile and desktop synchronization.
- Searchable metadata and optional AI-assisted indexing.
- Version history and recovery from accidental changes.
- Secure remote access without exposing storage directly to the public internet.
- Standard export formats that prevent platform lock-in.
- Separate permissions for private files, application data, and shareable content.

Self-hosting does not eliminate the need for backups. The system should maintain multiple copies across independent devices or locations, include at least one offline or immutable copy, and regularly verify that restoration works.

## Local-first AI

DannyOS should use local language models on a MacBook or other available computers when local execution provides acceptable quality and latency.

Local AI should be considered for:

- Summarization and classification.
- Personal search and retrieval.
- Routine planning and drafting.
- Private document analysis.
- Extraction of structured data.
- Background processing that would otherwise consume paid tokens.

Hosted models should remain available when a task requires stronger reasoning, larger context, current provider capabilities, or performance unavailable locally. A model router should select between local and hosted models using privacy, capability, latency, availability, and cost—not token cost alone.

## Phone-accessible AI workspace

The platform should provide a secure space where local and hosted assistants can be messaged from a phone.

The workspace should:

- Preserve conversation history and searchable context.
- Identify which model handled each response.
- Allow conversations to reference approved DannyOS data.
- Support internet research with source links and clear separation between retrieved facts and model inference.
- Support tool use through scoped, auditable permissions.
- Synchronize across phone and desktop clients.
- Continue queued work when the phone is disconnected.
- Show task progress, failures, approvals, and completed outputs.

External actions—such as sending messages, changing records, purchasing items, or controlling devices—should remain approval-gated unless a narrowly defined automation has been explicitly authorized.

## Unified dashboard

The dashboard is the primary operational view of DannyOS. It should consolidate the state of the platform without forcing every underlying system into the same database.

The dashboard should present:

- Current priorities and unresolved decisions.
- Upcoming calendar commitments and required preparation.
- Relationship, health, project, storage, and automation summaries.
- Recent activity and changes across connected systems.
- Predictions, trends, anomalies, and recommendations.
- The source data and reasoning behind important recommendations.
- AI tasks currently running locally or remotely.
- Storage, synchronization, backup, and service health.
- Actions awaiting approval.
- A searchable audit trail of automated and user-initiated changes.

Predictions must be labeled as predictions rather than facts. Automated controls should be reversible where possible, and the dashboard should make it clear what changed, why it changed, and which system performed the action.

## Integration model

DannyOS should treat Notion, Google Calendar, Gmail, Spotify, native contact systems, and future services as integrations around a private core rather than as the permanent owners of all platform data.

Each integration should define:

- Data read by DannyOS.
- Data written back to the provider.
- Sync direction and conflict resolution.
- Authentication and permission scope.
- Retention and deletion behavior.
- Failure and recovery behavior.
- Whether the integration is required or optional.

## Platform principles

- **Local-first where practical:** prioritize local storage and processing when they meet reliability and quality requirements.
- **Cloud-capable where useful:** retain secure remote access, synchronization, and hosted-model fallbacks.
- **User-controlled:** preserve exports, deletion controls, permission visibility, and provider independence.
- **Approval-gated:** require confirmation before consequential external actions.
- **Explainable:** expose sources, reasoning, model identity, and action history.
- **Resilient:** design for device loss, network loss, service failure, and restoration from backup.
- **Private by default:** keep personal data out of the public roadmap and minimize access granted to each component.
- **Neurodivergent by design:** reduce cognitive load, preserve context, support recovery, and make system state explicit and predictable.

## Initial delivery sequence

1. **Architecture inventory** — identify current data sources, devices, storage volume, integrations, and migration constraints.
2. **Secure remote foundation** — establish identity, device access, networking, secrets management, and audit logging.
3. **Self-hosted storage pilot** — migrate a noncritical file subset and validate synchronization, backup, and restoration.
4. **Local AI gateway** — expose selected local models through one authenticated interface with usage tracking.
5. **Phone AI client** — provide messaging, conversation history, research results, task status, and approvals.
6. **Read-only dashboard** — consolidate state before introducing controls.
7. **Android migration** — move core mobile workflows after data and recovery paths are verified.
8. **Controlled automation** — add reversible actions with narrow permissions and explicit approval rules.

## Open product decisions

- Which Android device and operating-system variant best support the intended integrations?
- Which data must remain available offline on the phone?
- Which files and photographs should migrate first?
- What storage capacity, upload bandwidth, and retention period are required?
- Which computer should host always-available services?
- Which local models meet the required quality and hardware constraints?
- Which tasks are permitted to fall back to paid hosted models?
- How should remote access work when the home network or primary host is unavailable?
- Which dashboard data requires real-time updates versus periodic synchronization?
- Which controls can be safely automated, and which must always require approval?
