# ADPL on Vercel

This project now uses:

- Static frontend files served by Vercel
- Vercel serverless functions in `api/`
- Firestore for shared persistent data
- Admin-only write access via a signed session token

## Required environment variables

Set these in Vercel Project Settings:

- `FIREBASE_KEY`: JSON string for a Firebase service account with Firestore access
- `ADMIN_PASSWORD`: password used by the admin login prompt
- `ADMIN_SESSION_SECRET`: secret used to sign admin session tokens

You can copy the shape from [.env.example](/C:/Users/HP/Desktop/league/.env.example).

## API structure

- `GET /api/data`
- `POST /api/admin/verify`
- `POST /api/admin/updatePredictions`
- `POST /api/admin/updateMatchResults`
- `POST /api/admin/updateSeasonActuals`
- `POST /api/admin/updatePreviousWinners`

## Hosting

1. Import the project into Vercel.
2. Add the environment variables above.
3. Deploy.

The frontend will stay publicly readable, while all data changes require a valid admin session created from `ADMIN_PASSWORD`.
