# Mona Personal Finances - Marketing Website

This is the official marketing website for Mona Personal Finances iOS app, hosted on GitHub Pages.

## Website Structure

```
website/
├── index.html          # Main landing page
├── privacy.html        # Privacy Policy
├── terms.html          # Terms of Service
├── support.html        # Support & FAQ
├── css/
│   └── style.css      # Main stylesheet
└── screenshots/       # App screenshots
```

## Features

- Modern, iOS-inspired design
- Fully responsive (mobile-first)
- Privacy-first messaging
- Fast loading with vanilla HTML/CSS/JS
- WCAG 2.1 AA accessible
- SEO optimized

## Deployment to GitHub Pages

### Option 1: Deploy from Repository Root

If your GitHub repository is `PersonalFinances`:

1. **Push your website files to GitHub:**
   ```bash
   git add website/
   git commit -m "Add marketing website"
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Click **Settings** > **Pages**
   - Under "Source", select **Deploy from a branch**
   - Select branch: **main**
   - Select folder: **/ (root)** or **/website** (if you want to serve from the website folder)
   - Click **Save**

3. **Configure for subdirectory (if needed):**
   - If GitHub Pages serves from root but your files are in `/website`:
   - Create a symlink or move files to root, OR
   - In Settings > Pages, use **/website** as the folder

4. **Your site will be live at:**
   ```
   https://[your-username].github.io/PersonalFinances/
   ```
   Or if using a custom domain, follow GitHub's custom domain setup.

### Option 2: Deploy from Separate Repository

If you want a cleaner URL like `https://[your-username].github.io/personal-finances-app/`:

1. **Create a new repository** named `personal-finances-app` (or any name you prefer)

2. **Copy website files to the new repository:**
   ```bash
   # From your PersonalFinances directory
   cp -r website/* /path/to/new/repo/
   cd /path/to/new/repo/

   git init
   git add .
   git commit -m "Initial website commit"
   git branch -M main
   git remote add origin https://github.com/[your-username]/personal-finances-app.git
   git push -u origin main
   ```

3. **Enable GitHub Pages:**
   - Same steps as Option 1, but select **/ (root)** as the folder

4. **Your site will be live at:**
   ```
   https://[your-username].github.io/personal-finances-app/
   ```

### Option 3: Use GitHub Pages with Custom Domain

1. **Purchase a domain** (e.g., `personalfinances.app`)

2. **Configure DNS:**
   - Add the following DNS records at your domain provider:
   ```
   A     @     185.199.108.153
   A     @     185.199.109.153
   A     @     185.199.110.153
   A     @     185.199.111.153
   CNAME www   [your-username].github.io
   ```

3. **Configure GitHub Pages:**
   - Go to Settings > Pages
   - Under "Custom domain", enter your domain
   - Check "Enforce HTTPS"

4. **Your site will be live at your custom domain**

## What to Update Before Going Live

### Critical Updates

1. **App Store Link** (in `index.html`):
   - Search for `#download` in the file
   - Replace with your actual Mona Personal Finances App Store URL:
     ```html
     <a href="https://apps.apple.com/app/idXXXXXXXXX" class="btn btn-primary">
     ```

2. **Open Graph Meta Tags** (in `index.html` `<head>`):
   - Update the `og:url` with your actual website URL
   - Optionally add `og:image` with a preview image for Mona

3. **Privacy Policy Date** (in `privacy.html`):
   - Currently set to January 7, 2026
   - Update to your actual publication date

4. **Terms of Service Date** (in `terms.html`):
   - Currently set to January 7, 2026
   - Update to your actual publication date

### Optional Updates

5. **Favicon** (in `index.html` `<head>`):
   - Replace the placeholder favicon with your actual app icon
   - Create a proper `favicon.ico` file and add:
     ```html
     <link rel="icon" type="image/x-icon" href="favicon.ico">
     ```

6. **App Icon in Hero** (optional):
   - Consider adding your app icon as an image in the hero section
   - Replace the screenshot placeholder in the hero-icon section

7. **Analytics** (optional):
   - Add Google Analytics or other tracking code if needed
   - Add to the `<head>` section of all HTML files

8. **Social Media Links** (optional):
   - Add Twitter, Facebook, or other social media links to footer

## Testing Before Launch

### Local Testing

1. **Open `index.html` in a browser:**
   ```bash
   cd website
   open index.html  # macOS
   # or use a local server
   python3 -m http.server 8000
   ```

2. **Test all pages:**
   - [ ] Index page loads correctly
   - [ ] All internal links work
   - [ ] Screenshots display properly
   - [ ] Mobile responsive (test on different screen sizes)
   - [ ] Privacy policy loads
   - [ ] Terms of service loads
   - [ ] Support page loads
   - [ ] All navigation links work
   - [ ] Footer links work

3. **Test interactions:**
   - [ ] Mobile menu toggle works
   - [ ] Smooth scrolling works
   - [ ] Hover effects work
   - [ ] All buttons are clickable

### Cross-Browser Testing

Test on:
- [ ] Safari (macOS/iOS)
- [ ] Chrome
- [ ] Firefox
- [ ] Edge

### Mobile Testing

Test on:
- [ ] iPhone (Safari)
- [ ] Android (Chrome)
- [ ] iPad

## Performance Optimization

The website is already optimized for performance:
- No external dependencies
- Vanilla CSS and JavaScript
- Minimal file sizes
- Optimized images (screenshots)

### Optional: Further Optimize Screenshots

If screenshots are too large:
```bash
# Install ImageMagick or use online tools
for file in screenshots/*.png; do
  convert "$file" -quality 85 -resize 1200x "$file"
done
```

## SEO Checklist

- [x] Meta descriptions on all pages
- [x] Semantic HTML structure
- [x] Alt text on images
- [x] Proper heading hierarchy (h1, h2, h3)
- [ ] Submit sitemap to Google Search Console (after launch)
- [ ] Add robots.txt if needed

### Create a sitemap.xml (optional)

Create `website/sitemap.xml`:
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://[your-username].github.io/PersonalFinances/</loc>
    <changefreq>monthly</changefreq>
    <priority>1.0</priority>
  </url>
  <url>
    <loc>https://[your-username].github.io/PersonalFinances/privacy.html</loc>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://[your-username].github.io/PersonalFinances/terms.html</loc>
    <changefreq>monthly</changefreq>
    <priority>0.8</priority>
  </url>
  <url>
    <loc>https://[your-username].github.io/PersonalFinances/support.html</loc>
    <changefreq>weekly</changefreq>
    <priority>0.9</priority>
  </url>
</urlset>
```

## Maintenance

### Regular Updates

1. **Update Privacy Policy** when you make changes to data collection
2. **Update Terms** when you add new features or change policies
3. **Update FAQ** in support.html as users ask new questions about Mona
4. **Update Screenshots** when you release major UI updates
5. **Add Release Notes** for major updates (consider a blog/news section)

### Monitoring

After launch, monitor:
- Google Search Console for SEO performance
- Google Analytics for traffic (if implemented)
- Contact email for support requests
- App Store reviews for common questions to add to FAQ

## Support

For questions about the website:
- Email: zeyar.oo.p@gmail.com

## License

© 2026 Zeyar Oo. All rights reserved.

---

## Quick Start Checklist

Before deploying to GitHub Pages:

1. [ ] Update App Store link in `index.html` (search for `#download`)
2. [ ] Update Open Graph URL in `index.html` meta tags
3. [ ] Verify all screenshots are optimized
4. [ ] Test website locally
5. [ ] Test on mobile devices
6. [ ] Push to GitHub
7. [ ] Enable GitHub Pages in repository settings
8. [ ] Verify site is live
9. [ ] Test all links on live site
10. [ ] Submit to Google Search Console
11. [ ] Share your website URL in App Store listing

**Current placeholder App Store link:** `#download` (needs to be replaced with actual URL)

Good luck with your launch! 🚀
