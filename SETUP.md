# How to Fix Quote Fetching

The quotes are failing because Yahoo Finance blocks direct browser requests. Here's how to fix it:

## Quick Fix: Deploy a Free Cloudflare Worker

1. **Sign up at Cloudflare Workers** (free)
   - Go to https://workers.cloudflare.com
   - Create a free account

2. **Create a new Worker**
   - Click "Create a Service"
   - Name it "yahoo-finance-proxy"

3. **Deploy the proxy code**
   - Click "Quick Edit"
   - Copy the code from `cloudflare-worker.js` in this repository
   - Paste it and click "Save and Deploy"

4. **Update your dashboard**
   - Your worker URL will be: `https://yahoo-finance-proxy.[your-subdomain].workers.dev`
   - Open the portfolio dashboard
   - Go to Settings tab
   - Replace the proxy URL with your Cloudflare Worker URL
   - Click Refresh

## Alternative Solutions

### Local Testing with CORS Anywhere
```bash
npx cors-anywhere
```
Then use `http://localhost:8080/https://query1.finance.yahoo.com` as proxy URL

### Free API Alternatives
- **Alpha Vantage**: https://www.alphavantage.co/ (5 requests/min free)
- **IEX Cloud**: https://iexcloud.io/ (50,000 messages/month free)
- **Twelve Data**: https://twelvedata.com/ (800 requests/day free)