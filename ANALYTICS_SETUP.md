# Analytics Setup Guide

Your website is configured to support multiple analytics providers. Follow these instructions to enable visitor tracking.

## Recommended: Pirsch (Privacy-Friendly)

**Why Pirsch?**
- ✅ Privacy-first, GDPR compliant
- ✅ No cookies required
- ✅ Lightweight and fast
- ✅ Simple, clean dashboard
- ✅ Free tier available

**Setup Steps:**

1. Sign up at https://pirsch.io
2. Add your website: `https://felixytang.github.io/academic-website/`
3. Copy your Site ID (looks like: `aBcD1234XyZ`)
4. Edit `config/_default/params.yaml`:
   ```yaml
   analytics:
     pirsch:
       site_id: "YOUR_PIRSCH_SITE_ID"
   ```
5. Commit and push to GitHub

## Alternative: Google Analytics 4

**Setup Steps:**

1. Create account at https://analytics.google.com
2. Set up a GA4 property
3. Get your Measurement ID (format: `G-XXXXXXXXXX`)
4. Edit `config/_default/params.yaml`:
   ```yaml
   analytics:
     google:
       measurement_id: "G-XXXXXXXXXX"
   ```
5. Enable privacy features:
   ```yaml
   privacy:
     enable: true
     anonymize_analytics: true
   ```
6. Commit and push to GitHub

## Other Supported Analytics

### Plausible Analytics
```yaml
analytics:
  plausible:
    domain: "felixytang.github.io"
```

### Fathom Analytics
```yaml
analytics:
  fathom:
    site_id: "YOUR_FATHOM_ID"
```

### Microsoft Clarity
```yaml
analytics:
  clarity:
    project_id: "YOUR_CLARITY_ID"
```

## Testing Your Analytics

After deployment:

1. Visit your website
2. Navigate to a few pages
3. Check your analytics dashboard (may take 5-30 minutes for first data)
4. Verify visitor tracking is working

## Privacy Considerations

**If using Google Analytics:**
- Enable anonymize_analytics in params.yaml
- Consider adding a privacy policy page
- Comply with GDPR/CCPA requirements

**If using Pirsch/Plausible/Fathom:**
- These are privacy-first by default
- No cookie banners required
- GDPR compliant out of the box

## Current Configuration

Your `config/_default/params.yaml` is already set up with placeholders. Just add your Site ID/Measurement ID to activate analytics.

## Next Steps

1. Choose an analytics provider
2. Sign up and get your tracking ID
3. Update `config/_default/params.yaml`
4. Commit and push to GitHub
5. Verify tracking after deployment

**Recommendation:** Start with Pirsch for hassle-free, privacy-compliant analytics.
