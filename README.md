# NestJS Standalone Web Scraper

A standalone CLI-based web scraper built with NestJS, leveraging its modular architecture and dependency injection to extract image URLs from webpages. This application uses `yargs` for command-line input handling and `cheerio` for HTML parsing.

## Features
- Extract image URLs from any webpage.
- Optionally save the scraped URLs to a file.
- Lightweight, standalone design without an HTTP server.
- Built with a modular and maintainable structure.

## How It Works
### Main Entry Point: `main.ts`
The application is initialized using `NestFactory.createApplicationContext`, which allows the use of NestJS features without starting an HTTP server. Command-line arguments are parsed and passed to the `ScraperService` to perform the scraping.

### Command-Line Arguments: `args.ts`
Uses `yargs` to handle command-line inputs:
- `--url` (required): The URL to scrape images from.
- `--save` (optional): Saves the scraped image URLs to a file if specified.

### Root Module: `app.module.ts`
Defines the application's structure, importing and providing necessary services.

### Scraping Logic: `scraper.service.ts`
Encapsulates the scraping functionality using `axios` to fetch HTML and `cheerio` to extract image URLs. If the `--save` flag is used, the scraped URLs are written to a file.

## Installation
1. Clone the repository

2. Install dependencies:
   ```bash
   pnpm install
   ```

## Usage
### Compile the TypeScript Code
```bash
pnpm run build
```

### Run the Application
#### Basic Usage
Scrape image URLs from a webpage:
```bash
node dist/main.js --url=https://example.com
```

#### Save Results to a File
Save the scraped image URLs to `images.txt`:
```bash
node dist/main.js --url=https://example.com --save
```

## Extending the Application
This scraper can be easily extended to:
- Download images from URLs.
- Handle pagination or dynamic content.
- Integrate with APIs for further processing.

## Conclusion
This project demonstrates the flexibility of NestJS beyond server-based applications, showcasing how its features can be leveraged to build robust and maintainable CLI tools. With its modular design, this web scraper is a foundation for more complex and powerful scraping utilities.
