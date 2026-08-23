# The History Desk - Substack Planner

## Setup on Netlify

1. Push this folder to a new GitHub repo (e.g. `helloallyson/history-desk`)
2. Connect the repo to Netlify (same as your other projects)
3. Add your Anthropic API key as an environment variable:
   - Go to **Site settings > Environment variables**
   - Add: `ANTHROPIC_API_KEY` = your key from console.anthropic.com
4. Deploy! The site will auto-build from the root.

## How it works

- `index.html` - The full dashboard (single file, localStorage for state)
- `netlify/functions/generate-article.js` - Serverless function that proxies AI requests to the Anthropic API
- `netlify.toml` - Build config

## AI Article Generation

The dashboard auto-detects where it's running:
- **Inside Claude's chat**: Uses the direct Anthropic API (no key needed)
- **On Netlify**: Routes through `/.netlify/functions/generate-article` using your API key

Click any post in the calendar, schedule, president tracker, or topic bank to open the article writer.
