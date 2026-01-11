# Rougemont Advisory Website

Professional website for Rougemont Advisory - Growth Advisory for Climate Tech

## Overview

This is a modern, interactive website built with HTML, CSS, and vanilla JavaScript. Features include:
- Animated hero section with particle effects
- Smooth scroll animations
- Responsive design
- Interactive service cards
- Contact form
- Professional layout inspired by leading investment banks

## File Structure

```
rougemont-website/
├── index.html          # Main HTML file
├── styles.css          # All CSS styles and animations
├── script.js           # JavaScript for interactivity
└── README.md          # This file
```

## Deployment Instructions

### Step 1: GitHub Setup

1. Create a new repository on GitHub (e.g., `rougemont-website`)
2. Initialize git in your local project folder:
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/rougemont-website.git
   git push -u origin main
   ```

### Step 2: Vercel Deployment

1. Go to [vercel.com](https://vercel.com) and sign up/login
2. Click "Add New" → "Project"
3. Import your GitHub repository
4. Configure project:
   - Framework Preset: **Other** (or leave as detected)
   - Root Directory: `./` (leave as default)
   - Build Command: Leave empty (static site)
   - Output Directory: Leave empty (static site)
5. Click "Deploy"
6. Vercel will provide you with a deployment URL (e.g., `your-project.vercel.app`)

### Step 3: Cloudflare DNS Configuration

1. Log in to [Cloudflare](https://cloudflare.com)
2. Select your domain (`rougemontadvisory.co.uk`)
3. Go to **DNS** section
4. Add/Update DNS records:
   
   **For root domain (rougemontadvisory.co.uk):**
   - Type: `CNAME`
   - Name: `@`
   - Target: `cname.vercel-dns.com`
   - Proxy status: Proxied (orange cloud)
   
   **For www subdomain:**
   - Type: `CNAME`
   - Name: `www`
   - Target: `cname.vercel-dns.com`
   - Proxy status: Proxied (orange cloud)

5. Save the DNS records

### Step 4: Connect Custom Domain in Vercel

1. In your Vercel project dashboard, go to **Settings** → **Domains**
2. Add your domain: `rougemontadvisory.co.uk`
3. Add www subdomain: `www.rougemontadvisory.co.uk`
4. Vercel will verify the DNS configuration
5. SSL certificate will be automatically provisioned (may take a few minutes)

### Step 5: Cloudflare SSL/TLS Settings

1. In Cloudflare, go to **SSL/TLS** → **Overview**
2. Set encryption mode to **Full** or **Full (strict)**
3. Go to **SSL/TLS** → **Edge Certificates**
4. Enable:
   - Always Use HTTPS: **On**
   - Automatic HTTPS Rewrites: **On**
   - Opportunistic Encryption: **On**

## Verification

Once DNS propagates (can take up to 48 hours, usually much faster):
- Visit `https://rougemontadvisory.co.uk` - should load your website
- Visit `https://www.rougemontadvisory.co.uk` - should also work

## Making Updates

To update your website:

1. Make changes to your local files
2. Commit and push to GitHub:
   ```bash
   git add .
   git commit -m "Description of changes"
   git push
   ```
3. Vercel will automatically redeploy your site

## Customization Guide

### Colors
Edit CSS variables in `styles.css` (lines 1-11):
```css
--deep-ocean-blue: #0A3D62;  /* Primary brand color */
--dark-green: #2E7D32;        /* Secondary color */
--charcoal: #2C3E50;          /* Neutral color */
```

### Content
- Hero section: Edit `index.html` lines 33-58
- Services: Edit `index.html` lines 72-144
- About section: Edit `index.html` lines 199-237
- Contact info: Edit `index.html` lines 264-307

### Images
To add images:
1. Create an `images/` folder
2. Add your images
3. Update image paths in HTML:
   ```html
   <img src="images/your-image.jpg" alt="Description">
   ```

### Adding Logo
Replace the text logo with an image:
```html
<!-- In navigation (line 23) -->
<div class="nav-logo">
    <a href="#home">
        <img src="images/logo.svg" alt="Rougemont Advisory">
    </a>
</div>
```

## Contact Form Setup

The contact form currently shows an alert. To make it functional:

1. **Option A: Use a form service**
   - [Formspree](https://formspree.io) - Free for 50 submissions/month
   - [Netlify Forms](https://www.netlify.com/products/forms/) - If you switch to Netlify
   - [EmailJS](https://www.emailjs.com) - Send emails directly from JavaScript

2. **Option B: Create a backend API**
   - Build an API endpoint (Node.js, Python, etc.)
   - Update `script.js` to POST to your API
   - Deploy API separately

Example with Formspree:
```html
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
```

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Performance Optimization Tips

1. **Add images**: Optimize images before uploading (use tools like TinyPNG)
2. **Lazy loading**: Add `loading="lazy"` to images
3. **Minification**: Consider minifying CSS/JS for production
4. **Caching**: Cloudflare handles this automatically

## Analytics Setup (Optional)

Add Google Analytics or Plausible:

```html
<!-- Add before </head> in index.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=YOUR_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'YOUR_ID');
</script>
```

## Troubleshooting

### Site not loading after DNS change
- Wait 24-48 hours for full DNS propagation
- Clear browser cache (Ctrl+Shift+R / Cmd+Shift+R)
- Check DNS propagation: https://dnschecker.org

### SSL Certificate issues
- Wait a few minutes after domain connection
- Ensure Cloudflare SSL is set to "Full" or "Full (strict)"
- Check Vercel project logs

### Mobile menu not working
- Ensure JavaScript is enabled
- Check browser console for errors (F12)

## Support

For technical support:
- Vercel: https://vercel.com/docs
- Cloudflare: https://support.cloudflare.com
- Web development: https://developer.mozilla.org

## License

© 2025 Rougemont Advisory. All rights reserved.

---

**Need help?** Contact your developer or web@rougemontadvisory.co.uk
