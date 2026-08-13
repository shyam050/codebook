# Codebook

An online course marketplace built with React — browse courses, add them to
a cart, check out, and view past orders from a dashboard. Originally built
against a `json-server` mock API; now backed by a real Spring Boot service.

**Backend repo:** [codebook-backend](https://github.com/<your-username>/codebook-backend)

## Tech stack

- React 18, React Router v6
- Context + reducers for cart and filter state (no Redux)
- Tailwind CSS
- react-toastify for notifications

## Features

- Product catalog with search, a featured-courses section, and a product
  detail page
- Cart (add/remove, running total) held in React Context
- Auth: register, login, guest login
- Protected routes: cart, checkout, and dashboard require login
- Dashboard listing a user's past orders
- Dark mode

## Pages

`Home`, `Products`, `ProductDetail`, `Cart` (with checkout), `Login`,
`Register`, `Dashboard`, `Order` (post-checkout summary), `PageNotFound`.

## Getting started

**Prerequisites:** Node.js, and the [codebook-backend](https://github.com/shyam050/codebook-backend)
service running (see that repo's README) — or any API that implements the
same contract.

```bash
npm install
cp .env.example .env   # sets REACT_APP_HOST and guest-login credentials
npm start
```

Opens on `http://localhost:3000`. `.env` points the app at the backend via
`REACT_APP_HOST` — update it if your backend isn't on `localhost:8080`.

```bash
npm run build   # production build
npm test        # run tests
```

## Environment variables

| Variable                   | Purpose                                      |
| -------------------------- | -------------------------------------------- |
| `REACT_APP_HOST`           | Base URL of the backend API                  |
| `REACT_APP_GUEST_LOGIN`    | Email used by the "Login As Guest" button    |
| `REACT_APP_GUEST_PASSWORD` | Password used by the "Login As Guest" button |

## Deploying for free

Vercel or Netlify both auto-detect this as a Create React App project with
zero config. Connect the repo, set `REACT_APP_HOST` to your deployed
backend's URL as an environment variable, and deploy. If the backend is on
Render, remember to add this frontend's live URL to the backend's
`CORS_ORIGINS` environment variable afterward, or every API call will be
blocked by CORS.

## Legacy: running against the json-server mock

`json-server` and `json-server-auth` are still in `devDependencies` from
before the real backend existed. Not needed anymore, but if you want to run
the original mock instead: `data/db.json` and `data/routes.json` hold the
fixture data and route rewrites it used.
