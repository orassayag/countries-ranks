# Instructions

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Initial Setup](#initial-setup)
3. [Environment Management](#environment-management)
4. [Available Commands](#available-commands)
5. [Script Usage Guide](#script-usage-guide)
6. [Troubleshooting](#troubleshooting)
7. [Advanced Configuration](#advanced-configuration)
8. [API Usage Tracking](#api-usage-tracking)
9. [Best Practices](#best-practices)

## Prerequisites

### System Requirements

- **Node.js**: Version 14 or higher (Next.js 10 compatibility)
- **Package Manager**: npm
- **Operating System**: macOS, Linux, or Windows
- **Memory**: 4GB RAM recommended
- **Disk Space**: 200MB for application and dependencies

## Initial Setup

### Install Dependencies

```bash
npm install
```

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

## Available Commands

### Development Commands

```bash
# Start development server
npm run dev

# Lint code
npm run lint
```

### Running Scripts

```bash
# Build for production
npm run build

# Start production server
npm run start
```

## Setup and Usage Instructions

1. Install dependencies using `npm install`.
2. Start the development server with `npm run dev`.
3. Open `http://localhost:3000` in your browser.
4. Use the search bar to filter countries.
5. Click on table headers to sort.

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

## Best Practices

- **Component Design**: Keep components focused and reusable.
- **Styling**: Use CSS Modules for scoped styles.
- **Data Fetching**: Use `getStaticProps` for static data and `useEffect` for client-side interactions.
- **Performance**: Optimize images and minimize client-side bundle size.

## Documentation

- **Next.js Documentation**: [nextjs.org/docs](https://nextjs.org/docs)
- **REST Countries API**: [restcountries.eu](https://restcountries.eu) (or current replacement)

## Extending the Application

- **New Features**: Add components to `src/components` and pages to `src/pages`.
- **API Integration**: Update data fetching logic in `src/pages/index.js` or `src/pages/country/[id].js`.
- **Styling**: Add global styles to `src/styles/globals.css`.

## External Resources

- [React Documentation](https://reactjs.org/docs/getting-started.html)
- [CSS Modules Guide](https://github.com/css-modules/css-modules)

## Troubleshooting

Refer to the [Common Issues and Solutions](#common-issues-and-solutions) section for specific problems.

## Last Updated

2026-05-31

## Version

1.0.0

## Notes

- This project uses an older Next.js stack (`next@10`, `react@17`).
- Keep compatibility in mind when adding modern APIs.
- If upgrading dependencies, test pages and dynamic routing thoroughly.

## Author

- **Or Assayag** - _Initial work_ - [orassayag](https://github.com/orassayag)
- Or Assayag <orassayag@gmail.com>
- GitHub: https://github.com/orassayag
- StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
- LinkedIn: https://linkedin.com/in/orassayag
