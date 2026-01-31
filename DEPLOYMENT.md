# GitHub Pages Deployment Setup

This repository has been configured to automatically deploy to GitHub Pages when changes are pushed to the `main` branch.

## One-Time Setup Required

To enable GitHub Pages deployment, you need to configure it in your repository settings:

1. Go to your repository on GitHub: https://github.com/skar-23/restaurant-demo
2. Click on **Settings** tab
3. In the left sidebar, click on **Pages** under "Code and automation"
4. Under "Build and deployment":
   - **Source**: Select "GitHub Actions"
5. Save the changes

## How It Works

- The GitHub Actions workflow (`.github/workflows/deploy.yml`) automatically builds and deploys your site when you push to the `main` branch
- The site will be available at: `https://skar-23.github.io/restaurant-demo/`
- You can also manually trigger the deployment using the "Actions" tab on GitHub

## Local Development

The project uses Vite with a base path configured for GitHub Pages:

```bash
# Install dependencies
npm install

# Run development server (runs on localhost without the base path)
npm run dev

# Build for production (includes the /restaurant-demo/ base path)
npm run build

# Preview production build locally
npm run preview
```

## Configuration

The following files have been configured for GitHub Pages deployment:

1. **vite.config.ts**: Added `base: "/restaurant-demo/"` to ensure assets load correctly on GitHub Pages
2. **.github/workflows/deploy.yml**: GitHub Actions workflow that builds and deploys the site

## Troubleshooting

If the deployment fails:
1. Check the "Actions" tab on GitHub to see error messages
2. Ensure GitHub Pages is enabled in repository settings
3. Verify that the workflow has proper permissions (should be configured automatically)
