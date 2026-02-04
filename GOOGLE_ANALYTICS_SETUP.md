# Google Analytics Setup Guide for Valentine's Project

## Step 1: Create Google Analytics Account

1. Go to [Google Analytics](https://analytics.google.com/)
2. Sign in with your Google account
3. Click "Start measuring"
4. Enter account name (e.g., "Valentine's Project")
5. Click "Next"

## Step 2: Create Property

1. Enter property name (e.g., "Valentine's Website")
2. Select your time zone and currency
3. Click "Next"

## Step 3: Choose Business Details

1. Select industry category (e.g., "Arts & Entertainment")
2. Choose business size
3. Click "Next"

## Step 4: Set Up Data Stream

1. Choose "Web" platform
2. Enter your website URL (e.g., `https://yourdomain.com/valentine.html`)
3. Enter stream name (e.g., "Valentine's Site")
4. Click "Create stream"

## Step 5: Get Your Measurement ID

After creating the stream, you'll see your **Measurement ID** (format: `G-XXXXXXXXXX`)

## Step 6: Update Your HTML Code

Replace `GA_MEASUREMENT_ID` in two places in `valentine.html`:

1. **Line 10**: In the gtag script URL
2. **Line 15**: In the gtag config call
3. **Line 524**: In the AnalyticsTracker class

Replace all instances of:
```javascript
'GA_MEASUREMENT_ID'
```

With your actual Measurement ID:
```javascript
'G-XXXXXXXXXX'
```

## Step 7: Test Your Setup

1. Open `valentine.html` in your browser
2. Open Google Analytics Realtime reports
3. You should see your visit appear within 30 seconds

## What's Being Tracked

### Page Views
- **Home page**: When users land on the main page
- **Question page**: When someone views a Valentine's question
- **Response pages**: When users see yes/no responses
- **Sender notifications**: When senders view response notifications

### Events Tracked
- `valentine_link_created`: When someone creates a new Valentine's link
- `valentine_response_yes`: When someone responds "Yes"
- `valentine_response_no`: When someone responds "No"
- `link_copied`: When someone copies a Valentine's link
- `response_link_copied`: When someone copies a response link
- `link_shared`: When someone shares a link
- `response_shared`: When someone shares a response

### Custom Parameters
- **from**: Sender's name
- **to**: Recipient's name

## Step 8: View Your Analytics

Go to Google Analytics dashboard to see:
- **Realtime**: Current visitors and their actions
- **Reports**: Detailed analytics over time
- **Events**: User interaction tracking
- **Audience**: Visitor demographics and behavior

## Privacy Notes

- No personal information is stored permanently
- Names are only used for event tracking
- Consider adding a privacy policy to your website
- You can disable analytics by removing the tracking code

## Optional: Enhanced E-commerce Setup

If you want to track conversion funnels:
1. Go to Admin → E-commerce Settings
2. Enable Enhanced E-commerce
3. Set up conversion goals for "Yes" responses

## Troubleshooting

**Not seeing data?**
- Check that your Measurement ID is correct
- Ensure you're not using an ad blocker
- Wait 24-48 hours for some reports to populate
- Check the Realtime report for immediate verification

**Events not showing?**
- Verify the Measurement ID is updated in all three places
- Check browser console for JavaScript errors
- Test by clicking buttons and checking Realtime Events report
