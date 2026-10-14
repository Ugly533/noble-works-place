# Noble Works Place — Random Joke Generator

This repository contains a small Random Joke Generator with two ways to host:

- Static client-only site (index.html) — suitable for GitHub Pages or Netlify.
- Server-backed Express app (server.js + public/) — suitable for Render or any Node host.

Deploying to GitHub Pages

1. Using the repository's main branch (docs/ folder):
   - Move `index.html` into a `docs/` folder on the `main` branch (or set the Pages source to the root if you prefer).
   - Go to the repository Settings → Pages and choose the `main` branch and `/docs` folder (or root) as the source.
   - The site will be available at `https://<your-username>.github.io/<repo-name>`.

2. Or, create a `gh-pages` branch and put `index.html` at the root of that branch. GitHub Pages will serve it automatically.

Deploying to Netlify (static)

1. Connect your GitHub repository to Netlify.
2. Set the build command to none and the publish directory to `/` (or leave default for a single `index.html`).
3. Netlify will build and publish the static `index.html`. Alternatively, you can drag-and-drop `index.html` in Netlify's deploy UI.

Deploying to Netlify (server)

Netlify does not run long-lived Node servers. For the server-backed version you should use Render, Heroku, Fly, or similar platforms. For APIs, consider using Netlify Functions.

Deploying to Render (recommended for server.js)

1. Create a new Web Service on Render and connect your GitHub repository.
2. Choose the branch (`add-joke-generator`) and set the Start Command to `npm start`.
3. Render will detect `package.json` and install dependencies, then run `server.js`.

Local run

Install dependencies and run locally (server-backed):

```bash
npm install
npm start
```

Open `http://localhost:3000`.

Notes

- The static client uses `https://icanhazdadjoke.com/` which supports CORS and JSON responses.
- If you want me to configure GitHub Actions to auto-deploy to GitHub Pages or set up an automatic Netlify/Render deploy configuration, tell me and I will add the workflow files.
