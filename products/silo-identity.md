# SILO Identity

**Status: Functional authentication tested / Infrastructure stabilization pending (25 October 2026).**

A dedicated central identity entry point for the SINA / SILO ecosystem at **https://id.sinaebrahimi.com**. User-confirmed end-to-end journeys: Google OAuth; email registration and verification; email/password login; password recovery and reset; sign-out and repeat sign-in. Custom SILO confirmation and recovery email templates exist, backed by Zoho SMTP. Central fonts are hosted by SILO Shared Assets.

## Deployment and technical boundaries

- Dedicated HTTPS hostname and a reverse-proxy gateway on Docker/Coolify.
- Gateway currently forwards to the website's PR #50 preview container; this is **not** a finalized independent production deployment.
- Primary source repository: [SINA Web Platform](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website), [PR #50](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/pull/50).
- Identity provider is a dedicated Supabase Auth project. Working authentication does **not** mean all ecosystem products have cross-domain SSO yet.

## Roadmap (unscheduled)

1. [Security audit and independent deployment](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/56): harden cookie/session lifecycle, return URLs, permissions, RLS, anti-abuse, ingress and deployment.
2. [Premium authentication UX](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/57): redesign login, registration, verification, recovery and account views in bilingual responsive charcoal/white/burgundy SILO DNA; Vazirmatn/MJ Two, accessibility and polished interaction states.
3. [SSO rollout](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/58): first integrate SILO Trading Journal with safe token/session handoff and proper app-level entitlements, then other SILO applications.
4. [Website comments and moderation](https://github.com/sina-ebrahimi-l/sina-ebrahimi-website/issues/59): article/media replies, permission rules, moderation and anti-spam; separate product workstream.

All roadmap tasks are intentionally unscheduled. No claim of completed SSO or completed security audit.
