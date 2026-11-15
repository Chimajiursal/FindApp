# FIND & REUNITE INDIA — v0.3 implementation starter

A runnable engineering foundation for a Maharashtra-first missing-person coordination platform.
This is a development scaffold, **not a production or emergency-response service**. Do not enter real personal data or publish real alerts until the security, legal, safeguarding, staffing, and partner-launch gates in `docs/PRODUCTION-GATES.md` are complete.

## Stack
- `apps/web`: Next.js + TypeScript responsive web/PWA entry point
- `apps/api`: NestJS + TypeScript API
- `apps/mobile`: Expo React Native starter notes
- PostgreSQL + PostGIS, Redis, BullMQ (planned worker integration)
- OpenAPI contract in `contracts/openapi.yaml`
- Database baseline in `database/schema.sql`

## Start local infrastructure
Requirements: Node.js 22+, npm, Docker Desktop.

```bash
docker compose up -d postgres redis
```

## Start API
```bash
cd apps/api
npm install
npm run start:dev
```
API health: http://localhost:4000/v1/health

## Start web
```bash
cd apps/web
npm install
npm run dev
```
Web: http://localhost:3000

The web demo uses fictional/sample copy only. Intake currently validates client-side and does not create a case. The API health endpoint is implemented; domain endpoints are contract-first placeholders.

## Build order
1. Complete authentication, OTP, session security and staff MFA.
2. Implement case intake and encrypted field service.
3. Implement secure media upload, malware scan and metadata stripping.
4. Implement reviewer state machine and maker-checker public-profile approval.
5. Implement confidential sighting intake and triage.
6. Implement referral pack generation and approved partner channels.
7. Implement alert preview, explicit approval, idempotent dispatch, expiry and revocation.
8. Add payment adapter only for optional services; emergency registration stays free.
9. Complete mobile clients, accessibility, localization and offline-safe draft handling.
10. Pass all launch gates and independent VAPT before production.

## Critical safeguards
- Platform registration is not an FIR, police complaint, government notice, or investigation.
- In an emergency, direct users to 112. For a child in distress, 1098 is the Child Helpline integrated with ERSS-112. Sources are linked in `docs/INDIA-COMPLIANCE.md`.
- Never delay emergency action for payment, OTP, platform review or police-reference upload.
- Public case pages must be allow-listed projections; never serialize the private case object.
- Public alerts require human safeguarding review and two-person approval for high-risk/child cases.
- Do not publish reporter contact details, exact private address, precise location, sensitive family details or unreviewed allegations.
- No facial recognition, public face search, automated identity matching, predictive risk scoring or crowdsourced confrontation.
- A tip is a lead, not proof. Never instruct volunteers to approach, detain, follow or interrogate a person.
