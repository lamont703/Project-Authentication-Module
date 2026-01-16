<<<<<<< HEAD
# Project-Authentication-Module
=======
# Project Authentication Module (Supabase Backend)

This folder contains the Supabase project configuration and Edge Functions for the Authentication module.

## Prerequisites

- [Docker](https://www.docker.com/get-started) installed and running.
- [Supabase CLI](https://supabase.com/docs/guides/cli/getting-started) installed.

## Getting Started

### 1. Initialize Supabase locally

Run the following command in this directory:

```bash
supabase start
```

This will start the local Supabase stack (PostgreSQL, GoTrue, PostgREST, Realtime, etc.) using Docker.

### 2. Serve Edge Functions locally

To develop and test Edge Functions locally, use:

```bash
supabase functions serve
```

By default, the functions will be available at `http://localhost:55321/functions/v1/<function-name>`.

### 3. Environment Variables

Copy `.env.example` to `.env` if you need to set local environment variables for your functions.

```bash
cp .env.example .env
```

## Module Structure

- `supabase/config.toml`: Main project configuration (configured to use port 55321 range to avoid local conflicts).
- `supabase/functions/`: Source code for Edge Functions.
  - `hello-world/`: Example function for verification.
- `supabase/migrations/`: Database migrations (currently empty).

## Verification

To verify the setup:

1. Ensure Docker is running.
2. Run `supabase start`.
3. Test the example function:
   ```bash
   curl -i --location --request POST 'http://localhost:55321/functions/v1/hello-world' \
     --header 'Content-Type: application/json' \
     --header "Authorization: Bearer [ANON_KEY]" \
     --data '{"name":"Supabase"}'
   ```
   (Get the `ANON_KEY` by running `supabase status`)
>>>>>>> 2cbcbd6 (Initialize Supabase project for Authentication module)
