# Traffic Automation Pro

Traffic Automation Pro is a production-ready web automation platform for generating human-like browser traffic, simulating organic search behavior, and evaluating site response under automated conditions.

## Overview

- **Backend:** Node.js, Express, Playwright, and stealth plugins
- **Frontend:** React, Vite, and Tailwind CSS
- **Traffic modes:** Stealth, Storm, and Search Engine
- **Security:** SSRF protection, rate safeguards, and browser isolation
- **Usage:** Real-time SSE progress updates and browser interaction analytics

## Features

- Simulates human browsing activity with mouse movement, scroll, and click patterns
- Supports multiple automation workflows: stealth, high-volume storm traffic, and search engine visits
- Built-in IP and URL validation to avoid local/private resource access
- Streamed progress updates via server-sent events
- Modern React dashboard with history persistence and result summaries

## Installation

### Prerequisites

- Node.js 18 or newer
- npm 10 or newer

### Install dependencies

```bash
npm install
cd frontend && npm install
```

### Install Playwright browsers

```bash
npx playwright install chromium
```

### Start development

```bash
npm run dev
```

Open the frontend at `http://localhost:5176` and the backend API at `http://localhost:3006`.

## Build for production

```bash
npm run build
```

The frontend build output is written to `frontend/dist`. The backend serves the static site when `NODE_ENV=production`.

## API Endpoints

- `POST /api/automate` — trigger automation with JSON payload
- `GET /api/health` — health check
- `GET /api/my-ip` — returns detected client IP address

### Example request

```bash
curl -X POST http://localhost:3006/api/automate \
  -H "Content-Type: application/json" \
  -d '{"url":"https://example.com","options":{"visitCount":3,"loopCount":1,"maxBatchVisits":2,"trafficMode":"stealth"}}'
```

## Contribution

Please see [CONTRIBUTING.md](CONTRIBUTING.md) for repository contribution guidelines.

## License

This project is released under the MIT License. See [LICENSE](LICENSE) for details.
