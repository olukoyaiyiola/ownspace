# OwnSpace

Independent living made easier: a mobile-first first-apartment planning, curated shopping, concierge and publishing platform.

## Status

**Prototype / not yet deployed or production-tested.** Public source repository; do not commit secrets, real customer data or passwords. This is a streamlined implementation of the initial concept.

## Features

- Responsive homepage and move-in checklist
- Concierge, merchant, sponsor, service, digital product and bundle inquiry categories
- Published product listings with merchant/affiliate links
- Blog with draft and publish statuses
- Admin login and team roles: owner, admin, editor, partner, viewer
- D1 storage for users, sessions, posts, listings, leads, partners and revenue

The revenue ledger records entries manually; it does **not** process payments. The newsletter option captures inquiries, not email subscriptions. Automatic partner payouts and WhatsApp messaging are not implemented.

## Stack

Cloudflare Workers, Workers Static Assets, Cloudflare D1, vanilla JavaScript and CSS.

## Deployment (after verification)

1. Create a D1 database named `ownspace` in Cloudflare.
2. Replace `REPLACE_WITH_YOUR_D1_DATABASE_ID` in `wrangler.toml` with its actual ID.
3. Run `npm install`.
4. Apply the schema: `npx wrangler d1 execute ownspace --remote --file=./schema.sql`.
5. Create a strong setup secret: `npx wrangler secret put SETUP_KEY`. Do not commit the value.
6. Deploy with `npm run deploy`.
7. Visit `/admin.html`, expand **First-time owner setup**, and use the secret to create your owner account. Use a unique 12+ character password.
8. Log in, create a draft blog post, publish it, and test a concierge inquiry.

Before opening to real customers: add rate limiting / bot protection to public forms and login, review privacy and retention requirements, test roles and security, validate payment/referral arrangements, and complete mobile browser QA.

## Local development

`npm install` then `npm run db:local` and `npm run dev`.

## Collaboration

Public contributions are welcome via issues and pull requests. Never share passwords or Cloudflare secrets in GitHub issues.
