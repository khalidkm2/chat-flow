# Realtime Threads Chat

## Local setup

Docker is no longer required for PostgreSQL. The backend connects to Neon using
`DATABASE_URL`.

1. Create a Neon project and copy its pooled PostgreSQL connection string.
2. Copy `backend/.env.example` to `backend/.env` and fill in:
   - `DATABASE_URL`
   - `CLERK_PUBLISHABLE_KEY`
   - `CLERK_SECRET_KEY`
   - Cloudinary variables if image uploads are used
3. Copy `frontend/.env.example` to `frontend/.env` and set
   `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`.
4. Install dependencies and run migrations:

   ```powershell
   cd backend
   npm install
   npm run migrate
   ```

5. Start the backend and frontend in separate terminals:

   ```powershell
   cd backend
   npm run dev
   ```

   ```powershell
   cd frontend
   npm install
   npm run dev
   ```

The frontend runs at `http://localhost:4000` and the backend at
`http://localhost:5000`.
