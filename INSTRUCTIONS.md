# Instructions

## Setup Instructions

1. Open the project in your IDE.
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the app:
   ```bash
   npm run dev
   ```
4. Open `http://localhost:3000`.

## Configuration

This project does not currently require `.env` variables for local development.

Data is fetched from public REST Countries endpoints in:

- `src/pages/index.js`
- `src/pages/country/[id].js`

If you change data providers, update both pages accordingly.

## Running the Application

### Development Mode
```bash
npm run dev
```
Starts Next.js dev server with hot reload.

### Production Build
```bash
npm run build
```
Builds static/generated pages for production.

### Production Start
```bash
npm run start
```
Runs the production server.

## Key Application Flows

### Home Page (`/`)

- Loads country list at build time via `getStaticProps`.
- Supports search filtering by:
  - Country name
  - Region
  - Subregion
- Supports sorting columns:
  - Name
  - Population
  - Area
  - Gini

### Country Details (`/country/[id]`)

- Builds static paths from all country alpha-3 codes.
- Loads country details per route.
- Resolves and displays neighboring countries.

## Project Structure

```text
src/
├── components/
│   ├── CountriesTable/
│   ├── Layout/
│   └── SearchInput/
├── pages/
│   ├── country/
│   │   ├── [id].js
│   │   └── Country.module.css
│   ├── _app.js
│   └── index.js
└── styles/
    ├── globals.css
    └── Home.module.css
```

## Manual Test Checklist

Run through this before opening a pull request:

1. Home page loads countries list.
2. Search input filters by name/region/subregion.
3. Sorting toggles through desc -> asc -> none.
4. Clicking a country navigates to details page.
5. Country details show expected fields and borders.
6. Theme toggle switches and persists across reload.
7. `npm run build` completes successfully.

## Common Issues and Solutions

### Failed Fetch During Build

- Cause: REST Countries endpoint unavailable.
- Actions:
  - Retry later.
  - Verify outbound network access.
  - Replace endpoint URLs with active equivalent if needed.

### `next start` fails after code changes

- Ensure production build exists:
  ```bash
  npm run build
  npm run start
  ```

### Unexpected client-side errors

- Check browser console for null/undefined fields from API data.
- Confirm response shape still matches current component logic.

## Notes

- This project uses an older Next.js stack (`next@10`, `react@17`).
- Keep compatibility in mind when adding modern APIs.
- If upgrading dependencies, test pages and dynamic routing thoroughly.
