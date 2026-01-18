# Deploy to AWS Amplify

## Deployment Steps

### 1. Create Amplify App via Console

1. Go to [AWS Amplify Console](https://console.aws.amazon.com/amplify)
2. Click "New app" → "Host web app"
3. Select "GitHub" as the repository service
4. Authorize AWS Amplify to access your GitHub account
5. Select repository: `scott-tikitram/seacoast-availability-map`
6. Select branch: `main`
7. App name: `seacoast-availability-map`
8. Click "Next"

### 2. Build Settings

The `amplify.yml` file is already configured. Amplify will auto-detect it.

### 3. Review and Deploy

1. Review the settings
2. Click "Save and deploy"
3. Wait for deployment to complete (~2-3 minutes)

### 4. Custom Domain (Optional)

1. In the Amplify app, go to "Domain management"
2. Add your custom domain (e.g., `availability.seacoastrentals.com`)
3. Follow DNS configuration instructions

## Repository Information

- GitHub URL: https://github.com/scott-tikitram/seacoast-availability-map
- Branch: main
- Files:
  - index.html - Main application
  - seacoastrentalslogo.png - Logo image
  - CircleDolphinNoAlpha200.png - Loading spinner
  - amplify.yml - Build configuration

## Backend API

The site connects to the Public Availability API Lambda:
- Endpoint: (configured in index.html)
- No authentication required
- CORS enabled for all origins

## Environment Variables

No environment variables needed - the site is fully static and uses the public API.

## Testing

After deployment, test:
1. Map loads with all properties
2. Date navigation works
3. Availability filtering works
4. Location filtering works
5. Property modals open with descriptions
6. Advanced filters work (bedrooms, bathrooms, amenities)

## Redeployment

Simply push to the `main` branch:

```bash
git add .
git commit -m "Update message"
git push origin main
```

Amplify will automatically rebuild and deploy.
