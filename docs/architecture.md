# Architecture & Engineering Approach

This document intentionally stays above the level of production source code and privileged configuration.

## System boundaries

AfterFive can be understood as four connected layers:

1. **Event acquisition**  
   External event and ticketing sources provide candidate event data.

2. **Normalization and application data**  
   Source data is transformed into a consistent application model suitable for product use.

3. **Operations and moderation**  
   Admin and organizer workflows control quality, lifecycle, ownership, approval, featured state, and recurring behavior.

4. **Consumer experience**  
   The web application turns approved event data into a fast, mobile-oriented discovery experience.

## Design principles

### Production isolation
New functionality is developed and validated without casually mutating production data or configuration.

### Deterministic readiness
Operational readiness should be based on explicit checks rather than a cosmetic score.

### Controlled changes
Where practical, higher-impact editor changes can be previewed before being applied and supported by undo/redo behavior.

### Data quality is a product feature
Missing imagery, incomplete event records, duplicates, ownership problems, and source inconsistencies directly affect the consumer experience, so data health is surfaced operationally.

### Recurring events need explicit rules
Recurring series are modeled intentionally rather than relying on manual duplication. Frequency, occurrence count, ownership, and lifecycle defaults need predictable behavior.

## What is intentionally not public

This repository does not disclose:

- production database schema details that create unnecessary attack surface
- credentials or environment variables
- privileged API routes
- admin authentication mechanisms
- internal provider keys or configurations
- deployment secrets
- proprietary application source
- private operational scripts
- security-sensitive implementation details

That boundary allows the engineering work to be discussed without turning the production repository into an open-source codebase.
