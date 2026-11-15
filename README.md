# OwnSpace

**Independent living made easier.** A mobile-first platform for first-apartment planning, curated essentials, concierge requests, partner referrals, and editorial content.

## Project status

Early MVP foundation. Do not accept payments or collect sensitive customer information until security, data handling and end-to-end deployment have been tested.

## Planned stack

- Cloudflare Workers (API)
- Cloudflare D1 (database)
- Static frontend served through Workers Assets
- Role-based admin and blog publishing

## Deployment checklist

1. Add the application source files from the OwnSpace MVP package.
2. Create a D1 database named `ownspace`.
3. Configure the D1 binding and setup secret.
4. Apply the database schema.
5. Deploy with Wrangler.
6. Test public forms, admin authentication, role permissions and publishing.

The website code and schema are not yet present in this repository. This README is the initial repository setup commit.
