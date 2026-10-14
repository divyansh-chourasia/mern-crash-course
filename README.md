# Product store

A small product list. The page is React in `frontend/`. The API is Express in `backend/`, and the only resource is `/api/products`.

The home page loads every product and shows a card for each one. A card can be edited or deleted. With an empty collection, the page points you at `/create`. That form takes a name, a price, and an image URL, and posts them as JSON. Price is stored as a string. There is no account system.

The navbar switches the Chakra color mode between light and dark.

## Run

`npm run dev` and `npm start` are launched from the repo root. `backend/config/db.js` loads `.env` from that directory:

```
PORT=5000
MONGO_URI=...
```

`PORT` falls back to 5000.

`npm run dev` sets `NODE_ENV=development` and does not serve the page. Run the API and Vite separately:

```bash
npm install
npm run dev
```

```bash
cd frontend
npm install
npm run dev
```

Vite proxies `/api` to port 5000.

`npm run build` installs dependencies and writes the frontend to `frontend/dist`. `npm start` sets `NODE_ENV=production` and serves that build from the API.
