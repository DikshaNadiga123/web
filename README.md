# Web — Creative Developer

A responsive, monochrome portfolio landing page built with Next.js App Router. It features animated line art, a warped grid, ticker strips, a contact form, and a synthesized playable piano keyboard.

## Run locally

```bash
npm install
cp .env.example .env.local
npm run dev
```

On Windows, copy `.env.example` to `.env.local` with File Explorer or:

```powershell
Copy-Item .env.example .env.local
```

Fill in the MongoDB and SMTP values described below before testing contact submissions. Never commit `.env.local`.

## Contact form configuration

The `POST /api/contact` route stores submissions in the MongoDB `contacts` collection and sends a confirmation email and a notification email using SMTP. Configure these environment variables in `.env.local` for development and in the Vercel project settings for deployment:

| Variable | Purpose |
| --- | --- |
| `MONGODB_URI` | MongoDB connection string |
| `MONGODB_DB` | Database name (defaults to `portfolio`) |
| `SMTP_HOST` | SMTP server hostname |
| `SMTP_PORT` | SMTP port (defaults to `587`) |
| `SMTP_USER` | SMTP username |
| `SMTP_PASS` | SMTP password or app password |
| `SMTP_FROM` | Verified sender address |
| `CONTACT_EMAIL` | Inbox for portfolio contact notifications |

The form displays an explicit configuration error when these values are missing; no credentials are included in source.

## Validate and build

```bash
npm run lint
npm run build
```

## Deploy

Import this repository into Vercel, then add the contact form environment variables in **Project Settings → Environment Variables** before deploying.
