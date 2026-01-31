# GitHub Pages Deployment Setup

## What I've Done

I've configured your restaurant-demo project to deploy automatically to GitHub Pages. Here's what was set up:

1. **Vite Configuration** (`vite.config.ts`)
   - Added `base: "/restaurant-demo/"` for production builds
   - This ensures all assets load correctly on GitHub Pages

2. **GitHub Actions Workflow** (`.github/workflows/deploy.yml`)
   - Automatically builds and deploys your site when you push to the `main` branch
   - Uses GitHub Pages' official deployment actions
   - Builds your Vite app and uploads the `dist` folder

3. **Package Configuration** (`package.json`)
   - Added homepage field pointing to your GitHub Pages URL

## How to Enable GitHub Pages (Manual Steps Required)

After this PR is merged to the `main` branch, you'll need to enable GitHub Pages in your repository settings:

1. Go to your repository: https://github.com/skar-23/restaurant-demo
2. Click on **Settings** (in the top menu)
3. Scroll down to **Pages** (in the left sidebar)
4. Under **Build and deployment**:
   - **Source**: Select "GitHub Actions"
   - This will use the workflow I created to build and deploy your site

5. Save the changes

## What Happens Next

Once GitHub Pages is enabled and this PR is merged:
- The workflow will automatically run on every push to `main`
- Your site will be available at: **https://skar-23.github.io/restaurant-demo/**
- The build process typically takes 1-2 minutes

## Local Testing

To test the production build locally:

```bash
# Build the project
npm run build

# Preview the production build
npm run preview
```

The preview will show you exactly how the site will look on GitHub Pages.

## Troubleshooting

If the site doesn't load after deployment:
1. Check the Actions tab to see if the workflow completed successfully
2. Verify GitHub Pages is set to use "GitHub Actions" as the source
3. Make sure the repository is public (GitHub Pages free tier only works with public repos)
4. Clear your browser cache and try again

## Project Structure

- **Source code**: `/src`
- **Build output**: `/dist` (automatically generated, not committed to git)
- **Workflow**: `.github/workflows/deploy.yml`
