# Deployment Guide

This guide provides step-by-step instructions for deploying the Gloria Beans Coffee Store website to Railway or Vercel.

## 📦 Deployment Options

### Option 1: Deploy to Railway.app

**Railway** is a PaaS platform that makes deployment simple and instant for static websites.

#### Prerequisites
- A GitHub account
- A Railway account (free tier available)
- This repository connected to GitHub

#### Steps:

1. **Prepare the Repository**
   - Ensure all HTML and CSS files are committed
   - Ensure the `Images/` folder is included
   - Test the site locally before deploying

2. **Create New Project on Railway**
   ```bash
   # In your Railway dashboard, click "Create a new project"
   # Select "Deploy from GitHub repository"
   # Choose the gloria-beans-coffee-store repository
   ```

3. **Configure Build Settings**
   - In the project dashboard, click "Settings → Environment"
   - Update `RAILWAY_STATIC_BUILD` to `true`
   - This tells Railway to serve static files directly

4. **Settings Review**
   - Default build command: Leave as-is (or set to `echo "Static site ready"` if no build needed)
   - Root directory: Leave as `/` (or use `/dist` if you add one)
   - Deployment branch: `main`

5. **Deploy**
   - Click "Deploy" to start the deployment
   - Wait for the build to complete (this is usually instant for static sites)
   - Your site will be live at a `https://` subdomain

6. **Custom Domain (Optional)**
   - Go to Settings → Domains
   - Click "Add domain"
   - Add your custom domain (requires DNS configuration)

#### Railway Project Features:
- Automatic HTTPS
- Global CDN
- Analytics integration (free)
- Custom domains support
- Environment variables configuration

---

### Option 2: Deploy to Vercel.app

**Vercel** is another excellent PaaS platform optimized for static websites and edge deployments.

#### Prerequisites
- A GitHub account
- A Vercel account (free tier available)
- This repository connected to GitHub

#### Steps:

1. **Install Vercel CLI (Optional)**
   ```bash
   npm i -g vercel
   ```

2. **Deploy via Dashboard**
   - Go to [vercel.com/new](https://vercel.com/new)
   - Import the gloria-beans-coffee-store repository
   - Click "Deploy"

3. **Deploy via CLI (Alternative)**
   ```bash
   cd "E:\Portfolio Projects\Full Stack\gloria-beans-coffee-store"
   vercel
   ```
   - Follow the prompts (you can use defaults)
   - Update your environment if needed

4. **Configuration Options**
   - Build Command: For static sites, this can be empty: `echo "Ready"`
   - Output Directory: Leave as `/` (or create `dist/` folder if needed)
   - Install Command: Not needed for static HTML/CSS
   - Framework Preset: Leave unset or select "Other"

5. **Post-Deployment**
   - Vercel will provide a preview URL automatically
   - Click "Domains" to add your own custom domain (requires DNS change)

#### Vercel Project Features:
- Edge network deployment globally
- Automated SSL certificates
- Preview deployments for branches
- Analytics dashboard
- Git integration
- Team collaboration

---

### Option 3: Deploy to Netlify (Alternative)

If you prefer Netlify, these steps are similar:

```bash
# Install Netlify CLI
npm i -g netlify-cli

# Deploy
netlify deploy --prod
```

---

## 🛠️ Deployment Preparation

### 1. Site Optimization

#### Add SEO Meta Tags
Add this to the `<head>` of every page:
```html
<meta name="description" content="Gloria Beans - Premium Coffee Store Online">
<meta name="keywords" content="coffee, coffee beans, espresso, gourmet coffee">
<meta name="author" content="Gloria Beans Coffee Store">
<link rel="canonical" href="https://yourdomain.com">
```

#### Add Favicon Configuration
Ensure all pages have:
```html
<link rel="icon" href="/Images/favicon.svg" type="image/svg+xml">
```

### 2. Image Optimization

#### Update Image Paths
Change local paths to relative web paths:
```css
/* Before */
background-image: url('Images/coffee back.jpg');

/* After (after deployment) */
background-image: url('/static/Images/coffee-back.jpg');
```

### 3. Test Locally Again
```bash
# Serve the site locally
python -m http.server 8000
# Or with Live Server extension
```

## 🚦 Deployment Checklist

- [ ] All HTML files are properly formatted
- [ ] All CSS files are linked correctly
- [ ] Image paths are correct and accessible
- [ ] No local dependencies (images are in the repository)
- [ ] Site tested in multiple browsers
- [ ] Mobile responsiveness verified
- [ ] Navigation links tested
- [ ] SEO meta tags added
- [ ] Favicon configured
- [ ] Contact forms (if any) tested

## 🔧 Troubleshooting

### 404 Errors
- Check file permissions - ensure `Images/` folder is accessible
- Verify file paths are relative, not absolute
- Check for misnamed files in the deployment package

### Images Not Loading
- Ensure images are in the root or a known path
- Check image file extensions are correct
- Verify images are included in the deployment

### Style Issues
- Clear browser cache (Ctrl+F5)
- Check CSS file paths are correct
- Verify CDN delivery is working

### Deployment Failure
- Check Railway/Vercel logs for specific errors
- Verify GitHub repository is reachable
- Ensure deployment branch is correct

## 📊 Post-Deployment

### Verify Functionality
- Test all navigation links
- Verify images load correctly
- Check mobile responsiveness
- Test contact forms if implemented
- Verify external links work

### Monitor Performance
- Check deployment analytics
- Monitor image load times
- Ensure SEO ranking is achievable

### Set Up Redundancy
```bash
# With npm
npm i -g vercel
vercel --prod

# Railway handles this automatically
```

## 🔄 Continuous Deployment

### Automatic Deployments
Once deployed, maintain automatic deployments:

1. **Railway**
   - Changes auto-deploy from main branch
   - No further configuration needed

2. **Vercel**
   - Auto-deploys on push to linked branches
   - Preview URLs for every commit

3. **Netlify**
   - Auto-deploys on push to main branch
   - Previews for every pull request

### Manual Deployment (On-Demand)
```bash
# Railway
railway up

# Vercel
vercel --prod

# Netlify
netlify deploy --prod
```

## 🎯 Quick Start Commands

### Railway (Fastest Method)
1. Go to [railway.app](https://railway.app/new)
2. Connect GitHub repository
3. Accept default settings
4. Site is live automatically!

### Vercel (Recommended for Teams)
1. Go to [vercel.com/new](https://vercel.com/new)
2. Import GitHub repository
3. Click Deploy
4. Site is live with preview URLs!

## 📞 Support Resources

- **Railway Documentation**: https://docs.railway.app
- **Vercel Documentation**: https://vercel.com/docs
- **Common Issues**: Check provider's status page first

---

Ready to deploy? Choose your preferred platform and follow the simple steps above! 🎉