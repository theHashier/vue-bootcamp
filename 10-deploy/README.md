# Lab 10 — Deploy

## What this lab builds

This lab demonstrates how a Vue application is prepared for production using Vite.

During development the application runs with a dev server.  
For deployment the project must be built into static files.

The build step converts the Vue project into optimized HTML, CSS and JavaScript files.

These files can then be deployed to any static hosting provider.

## Development

Start the development server:

npm run dev

This starts the Vite dev server and enables hot reload for development.

## Production Build

Create the production build:

npm run build

After running this command Vite generates a new folder:

dist/

Example structure:

dist
├── index.html
└── assets
    ├── index-xxxxx.js
    └── index-xxxxx.css

The dist folder contains the optimized files that are deployed to a server.

## Preview Production Build

You can locally preview the production build with:

npm run preview

This serves the built files from the dist folder and simulates how the app runs in production.

## Deployment Concept

Development:

npm run dev

Production:

npm run build  
→ dist/ created  
→ deploy dist files

## Where Vue apps can be deployed

Because the output is static files, Vue apps can be hosted on many platforms:

- Netlify
- Vercel
- GitHub Pages
- AWS S3
- CloudFront
- Nginx
- Apache

## What we learned

- Running a Vue development server
- Building a production bundle with Vite
- Understanding the dist folder
- Previewing the production build locally
- Preparing a frontend application for deployment