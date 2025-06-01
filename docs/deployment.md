# Deployment Instructions

This document outlines how to deploy PaySurity services to Railway and Vercel.

## Railway (Backend Services)

1. Log in to Railway.
2. For each service (e.g., PaySurity-Core-API, PaySurity-Auth-Service, etc.):
   - Click **New Project** → **Deploy from GitHub**.
   - Select the repository (e.g., `rwbgoachic/PaySurity-Core-API`).
   - Configure environment variables:
     - `DATABASE_URL`, `PORT`, and any other service-specific variables.
   - Deploy and wait for the build to succeed.

3. After deploying all backend services, note their live URLs.

## Vercel (Frontend Services)

1. Log in to Vercel.
2. For each frontend (e.g., PaySurity-Admin-UI, PaySurity-POS-Restaurant-UI, etc.):
   - Click **New Project** → **Import Third-Party Git Repository**.
   - Select the corresponding repository (e.g., `rwbgoachic/PaySurity-Admin-UI`).
   - Vercel will auto-detect framework (Next.js).
   - Set any required environment variables.
   - Deploy and wait for it to go live.

3. Once all frontends are live, update service URLs in the Admin UI `.env` or through Vercel dashboard.

## Environment Variables

- **Common**:  
  - `NODE_ENV=production`

- **Core API / Auth / Payroll / Tax**:  
  - `DATABASE_URL`: PostgreSQL connection string.
  - `PORT`: Port number (e.g., `4000`, `5000`, `5500`, etc.).

- **Frontends**:  
  - `NEXT_PUBLIC_API_URL`: URL of the Core API service.

