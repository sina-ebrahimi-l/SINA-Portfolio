# AI Infrastructure Layer

## Overview

A shared infrastructure layer that lets multiple products reuse model access, speech processing and common AI capabilities without coupling every application to a single provider or implementation.

## Representative Systems

### LLM Router
A central routing layer for selecting model providers and fallback paths across internal services.

### SILO Speech Service
A shared speech-processing service for transcription, subtitle generation and voice-driven workflows.

### Sina Commander — AI Notification & Approval Bridge
A provider-neutral coordination capability that gives the owner a single mobile notification and decision channel for registered AI tasks. It tracks task milestones, signals unresolved decisions and possible execution stalls, records scoped owner responses, and reports completion. The Telegram delivery and owner-response workflow are verified in production.

The bridge supports authorized integrations rather than depending on a single model. Platform-mandated approvals remain in their original application; the system does not claim automatic visibility into every external AI conversation.

## Design Goals

- Reduce duplicated integration work
- Keep product code independent from provider-specific logic where possible
- Centralize reliability and fallback policy
- Make shared capabilities reusable across multiple products
- Keep cost and operating constraints visible at the infrastructure layer

## Public Boundary

Provider credentials, exact routing rules, private endpoints, fallback thresholds and production configuration are intentionally not published.

## Status

**In Production / Active Expansion**
