# SnapTik Pro — AI Text to Video

A Node.js + Express starter website using fal.ai's Wan 2.5 text-to-video endpoint.

## What is included
- Mobile-friendly SnapTik Pro frontend
- Text prompt, aspect ratio, duration (5/10 sec), resolution (480p/720p/1080p)
- Server-side fal.ai API key handling
- Queue-based generation and status polling
- MP4 preview and link to open/download the generated file
- Basic per-IP generation rate limit

## Requirements
- Node.js 18+
- A fal.ai account and API key
- A hosting provider that supports Node.js (for example Render)

## Run locally
1. Extract this ZIP.
2. Copy `.env.example` to `.env`.
3. Put your fal.ai key in `.env` as `FAL_KEY=...`.
4. In the project folder run:
   ```bash
   npm install
   npm start
   ```
5. Open `http://localhost:3000`.

## Deploy on Render
1. Upload the extracted project to a GitHub repository.
2. In Render, choose New > Web Service and connect that repository.
3. Build command: `npm install`
4. Start command: `npm start`
5. Add environment variable `FAL_KEY` with your actual fal.ai API key.
6. Deploy and open the Render URL.

## Important security and cost notes
- Never put `FAL_KEY` in `public/index.html` or any browser-side JavaScript.
- Never commit `.env`; `.gitignore` excludes it.
- Generation is not free. Check fal.ai model pricing and account balance before use.
- The included rate limit is only a basic safeguard. For a public production service, add user authentication, stronger abuse prevention, quotas, monitoring, and a reliable download proxy.
- The generated video URL is hosted by fal.ai. The page opens that MP4 URL; whether it downloads directly depends on the browser and remote server headers.
- This is a starter implementation, not a complete commercial service.

## Model documentation
https://fal.ai/models/fal-ai/wan-25-preview/text-to-video/api
