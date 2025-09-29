# Store Rating App

Monorepo containing a Vite React frontend and an Express + MySQL backend.

- Frontend: `Store_Rating_app/frontend/`
- Backend: `Store_Rating_app/backend/`

## Prerequisites
- Node.js 18+
- MySQL 8+

## Backend setup

1) Create `.env` in `Store_Rating_app/backend/` (example):
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_password
DB_NAME=store_rating_db
DB_PORT=3306

JWT_SECRET=replace_me
JWT_EXPIRES_IN=24h

PORT=5000
NODE_ENV=development

# Set to your Vite origin
CORS_ORIGIN=http://localhost:3001
```

2) Install and run:
```
cd Store_Rating_app/backend
npm install
npm run seed   # creates DB/tables and inserts sample users, stores, ratings
npm run dev    # starts the API on http://localhost:5000
```

Seeded accounts (password = `password`):
- Admin: `admin@storeapp.com`
- Store owner: `owner1@storeapp.com`
- Customer: `customer1@storeapp.com`

## Frontend setup
```
cd Store_Rating_app/frontend
npm install
npm run dev   # Vite dev server (check terminal for the exact URL, e.g. http://localhost:3001)
```

## Features
- Home with featured stores
- Store directory with search, sort, rating display
- Inline rating editor (per-card) with comments
- Add store (store owner or admin) and owner/admin delete
- Auth: register/login/change password (frontend demo uses local state unless wired to backend)

## Important
Currently the frontend uses `localStorage` via `frontend/src/services/localApi.js`. To persist stores/ratings in MySQL instead, replace usages with real HTTP calls to the backend (e.g., create `httpApi.js` and hook endpoints like `GET /stores`, `POST /stores`, `DELETE /stores/:id`, `POST/PUT /ratings`). Ensure `CORS_ORIGIN` in backend `.env` matches your Vite origin.

## GitHub
Initialize and push:
```
cd c:/Users/hp/Desktop/Roxiler_Web_Application
git init
git add .
git commit -m "Initial commit: Store Rating App"
git remote add origin https://github.com/<your_user>/Roxiler_Web_Application.git
git branch -M main
git push -u origin main
```
