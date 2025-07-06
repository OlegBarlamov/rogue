# Rogue Monorepo

A monorepo built with Turbo containing a React TypeScript frontend and a NestJS backend server.

## Structure

```
rogue/
├── apps/
│   ├── web/          # React TypeScript frontend (Vite)
│   └── server/       # NestJS backend server
├── packages/         # Shared packages (future use)
├── package.json      # Root package.json with workspaces
├── turbo.json        # Turbo configuration
└── README.md         # This file
```

## Prerequisites

- Node.js (v18 or higher)
- npm (v8 or higher)

## Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Install workspace dependencies:**
   ```bash
   npm install --workspace=web
   npm install --workspace=server
   ```

## Development

### Start all applications
```bash
npm run dev
```

### Start individual applications
```bash
# Start only the React frontend
npm run dev:web

# Start only the NestJS server
npm run dev:server
```

### Other commands
```bash
# Build all applications
npm run build

# Lint all applications
npm run lint

# Run tests
npm run test

# Clean build artifacts
npm run clean

# Format code
npm run format
```

## Applications

### Web App (React + TypeScript + Vite)
- **Port:** 3000
- **URL:** http://localhost:3000
- **Tech Stack:** React 18, TypeScript, Vite
- **Features:** Hot Module Replacement, TypeScript support

### Server App (NestJS)
- **Port:** 3001
- **URL:** http://localhost:3001
- **Tech Stack:** NestJS, TypeScript, Express
- **Endpoints:**
  - `GET /` - Hello World message
  - `GET /ping` - Ping endpoint returning pong with timestamp

## API Endpoints

### Server Endpoints

1. **GET /** - Returns "Hello World!"
2. **GET /ping** - Returns:
   ```json
   {
     "message": "pong",
     "timestamp": "2024-01-01T00:00:00.000Z"
   }
   ```

## Development Workflow

1. Start the development servers:
   ```bash
   npm run dev
   ```

2. The React app will be available at http://localhost:3000
3. The NestJS server will be available at http://localhost:3001
4. Test the ping endpoint: http://localhost:3001/ping

## Turbo Features

This monorepo uses Turbo for:
- **Caching:** Build outputs are cached for faster subsequent builds
- **Parallel execution:** Tasks run in parallel when possible
- **Dependency management:** Automatic dependency graph management
- **Incremental builds:** Only rebuild what changed

## Adding New Packages

To add a new package to the monorepo:

1. Create a new directory in `packages/`
2. Initialize with `npm init`
3. Add it to the workspace configuration in root `package.json`
4. Install dependencies and start developing

## Troubleshooting

If you encounter issues:

1. **Clear cache:** `npm run clean`
2. **Reinstall dependencies:** `rm -rf node_modules && npm install`
3. **Check ports:** Ensure ports 3000 and 3001 are available
4. **Check Node version:** Ensure you're using Node.js v18 or higher
