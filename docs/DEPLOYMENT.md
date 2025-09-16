# Deployment Guide

This document describes how to deploy the Claude Code Workshop website to various platforms.

## AWS Amplify Deployment (Recommended)

### Prerequisites
- AWS account
- GitHub repository
- Amplify CLI (optional)

### Deployment Steps

1. **Connect Repository**
   - Log in to AWS Amplify Console
   - Click "New App" > "Host web app"
   - Connect your GitHub repository
   - Select the main branch

2. **Build Configuration**
   - Amplify will automatically detect the `amplify.yml` file
   - Review the build settings (they should be correct by default)
   - Click "Next"

3. **Review and Deploy**
   - Review all settings
   - Click "Save and Deploy"
   - Wait for the build to complete

### Custom Domain (Optional)
1. In Amplify Console, go to "Domain management"
2. Add your custom domain
3. Configure DNS settings as instructed

## Static Hosting Alternatives

### Netlify
1. Connect your GitHub repository to Netlify
2. Set build command: `npm run build`
3. Set publish directory: `/`
4. Deploy

### Vercel
1. Import project from GitHub
2. Configure build settings (usually auto-detected)
3. Deploy

### GitHub Pages
1. Go to repository Settings > Pages
2. Select source branch (main)
3. Site will be available at `https://username.github.io/repository-name`

## Local Development Server

For local testing:

```bash
# Install dependencies
npm install

# Start development server
npm start

# Or with auto-open
npm run dev
```

## Environment Variables

This project doesn't require environment variables for basic deployment. If you need to add them:

### AWS Amplify
Add environment variables in the Amplify Console under App Settings > Environment variables

### Other Platforms
Follow the platform-specific documentation for environment variable configuration.

## Build Optimization

The website is optimized for static hosting:
- Minimal dependencies
- No build process required
- Optimized for CDN distribution
- Responsive design for all devices

## Troubleshooting

### Common Issues

**Build Fails**
- Check that all file paths are correct
- Ensure `package.json` has proper dependencies
- Verify `amplify.yml` configuration

**CSS/JS Not Loading**
- Check file paths in HTML
- Ensure files are in correct directories
- Clear browser cache

**404 Errors**
- Check `_redirects` file configuration
- Verify routing setup for SPA behavior

### Support

If you encounter issues:
1. Check the repository issues
2. Review deployment logs
3. Contact the maintainers