# SILO Identity

**Status: Production website integration verified / Broader Identity roadmap remains separate (13 November 2026).**

A dedicated central identity entry point for the SINA / SILO ecosystem at **https://id.sinaebrahimi.com**. User-confirmed end-to-end journeys: Google OAuth; email registration and verification; email/password login; password recovery and reset; sign-out and repeat sign-in. Custom SILO confirmation and recovery email templates exist, backed by Zoho SMTP. Central fonts are hosted by SILO Shared Assets.

## Deployment and technical boundaries

- Dedicated HTTPS hostname and a reverse-proxy gateway on Docker/Coolify.
- The gateway follows the current healthy production website release. The former preview-bound upstream is retired; a separately deployed Identity service is a distinct architectural workstream.
- Website integration: the completed [SINA Web Platform](sina-web-platform.md) at [sinaebrahimi.com](https://sinaebrahimi.com).
- Identity provider is a dedicated Supabase Auth project. Working authentication does **not** mean all ecosystem products have cross-domain SSO yet.

## Roadmap (unscheduled)

1. [Security audit and independent deployment](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/56): harden cookie/session lifecycle, return URLs, permissions, RLS, anti-abuse, ingress and deployment.
2. [Premium authentication UX](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/57): redesign login, registration, verification, recovery and account views in bilingual responsive charcoal/white/burgundy SILO DNA; Vazirmatn/MJ Two, accessibility and polished interaction states.
3. [SSO rollout](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/58): first integrate SILO Trading Journal with safe token/session handoff and proper app-level entitlements, then other SILO applications.
Existing website comments and moderation are part of the accepted production website. Further comment capabilities and broader Identity changes need their own scope; they do not reopen the completed public-site launch.

All roadmap tasks are intentionally unscheduled. No claim of completed SSO or completed security audit.
