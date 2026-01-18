# Sea Coast Rentals Availability Map

Public property availability viewer for Sea Coast Rentals.

## Features

- **Interactive Map View** - Google Maps with property markers and labels
- **List View** - Grid view of all properties
- **Real-time Availability** - Filter properties by date
- **Advanced Filtering** - Filter by location, bedrooms, bathrooms, sleeps, amenities
- **Property Details** - Full marketing descriptions from Guesty
- **Responsive Design** - Works on desktop and mobile

## Deployment

**App ID**: d18qchvq381wxg
**Default Domain**: https://d18qchvq381wxg.amplifyapp.com
**Custom Domain**: map.seacoastrentals.com (to be configured)

### Deploy to Amplify

The site is deployed to AWS Amplify. To complete the deployment:

1. **Connect to GitHub** (via AWS Console):
   ```bash
   # Go to: https://console.aws.amazon.com/amplify/home?region=us-east-1#/d18qchvq381wxg
   # Click "Connect repository"
   # Select: scott-tikitram/seacoast-availability-map
   # Branch: main
   ```

2. **Configure Custom Domain**:
   ```bash
   aws amplify create-domain-association \
     --app-id d18qchvq381wxg \
     --domain-name seacoastrentals.com \
     --sub-domain-settings prefix=map,branchName=main \
     --region us-east-1
   ```

3. **Update DNS**:
   - Add the CNAME record provided by Amplify to your DNS settings

## Repository

- **GitHub**: https://github.com/scott-tikitram/seacoast-availability-map
- **Branch**: main

## Backend API

- **Endpoint**: https://5kycaw6yb32f3p3nzlsfwrtfce0zzbyh.lambda-url.us-east-1.on.aws
- **Properties**: `/properties`
- **Reservations**: `/reservations`
- **Availability**: `/availability?date=YYYY-MM-DD`
- **Description**: `/properties/{propertyId}/description`

## Local Development

Simply open `index.html` in a web browser. No build process required.

## Updates

Push to the `main` branch to trigger automatic deployment:

```bash
git add .
git commit -m "Update message"
git push origin main
```

Amplify will automatically rebuild and deploy within 2-3 minutes.
