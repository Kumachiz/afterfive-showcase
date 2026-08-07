# Architecture & Engineering Approach

This document intentionally stays above the level of production source code and privileged configuration.

## System boundaries

AfterFive uses private application, data, integration, and content-operations layers to support its public consumer experience. Detailed boundaries, data flows, privileged workflows, and implementation choices are intentionally not documented here.

## Design principles

### Production isolation
New functionality is developed and validated without casually mutating production data or configuration.

### Operational quality
Data quality, controlled publishing, and regression safety are treated as product concerns without publishing the supporting internal workflows.

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
