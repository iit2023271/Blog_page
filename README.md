# Blog Website

A blog platform built with Express, EJS, and MongoDB — create, read, update, and delete articles, with Markdown rendering and URL slugs. This copy uses the standard MVC layout, so it runs as-is.

![Demo](screenshots/demo.png)

*Homepage rendered with sample articles (a live database was not connected for this screenshot).*

## Features

- **Article CRUD** — create, read, edit, and delete blog articles.
- **Markdown rendering** — write articles in Markdown; they render as clean HTML (via `marked`).
- **URL slugs** — each article gets a readable slug URL (via `slugify`).
- **Sanitized HTML** — rendered Markdown is sanitized (via `dompurify` + `jsdom`) so raw HTML in articles cannot inject scripts.
- **Bootstrap UI** — article cards, forms, and buttons styled with Bootstrap 5.
- **Method override** — HTML forms support PUT and DELETE via `method-override`.

## Tech Stack

- Node.js + Express 4
- EJS (templates)
- MongoDB + Mongoose (article storage)
- marked (Markdown → HTML)
- slugify (URL slugs)
- dompurify + jsdom (HTML sanitization)
- method-override
- Bootstrap 5 (frontend styling)

## Project Layout

```
server.js            # Express app entry, MongoDB connection, routes
models/article.js    # Mongoose article model
routes/articles.js   # Article CRUD routes
view/articles/       # EJS templates (index, show, new, edit)
```

## How to Run

```bash
npm install
```

The app connects to MongoDB at `mongodb://localhost/bharatInternDatabase` (see `server.js`) — make sure a local MongoDB instance is running first. Then:

```bash
node server.js
# then visit http://localhost:3000
```

## Notes

- This is the working MVC layout of the blog app: the folders match what `server.js` requires, so it starts without changes once MongoDB is running.
