# Deployment Instructions for Sand Dollar Technology Website

## 🚀 Deploying to GitHub Pages

### Step 1: Initialize Git Repository

```bash
cd C:\projects\sanddollartechnology
git init
git add .
git commit -m "Initial commit: Professional Sand Dollar Technology website"
```

### Step 2: Create GitHub Repository

1. Go to https://github.com/new
2. Repository name: `sanddollartechnology` (or your preferred name)
3. Keep it Public (required for free GitHub Pages)
4. **Do NOT** initialize with README, .gitignore, or license (we already have these)
5. Click "Create repository"

### Step 3: Push to GitHub

Replace `YOUR_USERNAME` with your GitHub username:

```bash
git remote add origin https://github.com/YOUR_USERNAME/sanddollartechnology.git
git branch -M main
git push -u origin main
```

### Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Click "Pages" in the left sidebar
4. Under "Build and deployment":
   - Source: Select "GitHub Actions"
5. The site will automatically build and deploy!

### Step 5: Access Your Site

Your site will be available at:
- `https://YOUR_USERNAME.github.io/sanddollartechnology/`

⏱️ First deployment takes 2-3 minutes. Check the "Actions" tab to monitor progress.

---

## 🔧 Before You Deploy - Quick Checklist

### Update Configuration

Edit `_config.yml`:

```yaml
url: "https://YOUR_USERNAME.github.io"  # Replace with your GitHub username
baseurl: "/sanddollartechnology"         # Or "" if using custom domain

# Update social links
social:
  github: YOUR_GITHUB_USERNAME
  linkedin: YOUR_LINKEDIN_HANDLE
  twitter: YOUR_TWITTER_HANDLE
```

### Set Up Contact Form

1. Go to [Formspree.io](https://formspree.io) and sign up
2. Create a new form
3. Copy your form ID
4. Edit `contact.md` and replace:
   ```html
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
   with your actual form ID

### Optional: Add Custom Domain

If you have a custom domain (e.g., `www.sanddollartechnology.com`):

1. Create file `CNAME` in root:
   ```
   www.sanddollartechnology.com
   ```

2. Update `_config.yml`:
   ```yaml
   url: "https://www.sanddollartechnology.com"
   baseurl: ""
   ```

3. Configure DNS with your domain provider:
   - Type: CNAME
   - Name: www
   - Value: YOUR_USERNAME.github.io

---

## 🎨 Customization Guide

### Adding Your Logo

1. Add logo image to `assets/images/logo.png`
2. Edit `_includes/header.html`:
   ```html
   <a href="{{ '/' | relative_url }}" class="logo">
       <img src="{{ '/assets/images/logo.png' | relative_url }}" alt="Sand Dollar Technology" style="height: 40px;">
   </a>
   ```

### Changing Colors

Edit `_sass/_variables.scss`:

```scss
$primary: #8B5CF6;        // Main purple color
$secondary: #EC4899;       // Pink accent
$accent: #06B6D4;          // Cyan accent
```

### Adding New Pages

1. Create `newpage.md`:
   ```markdown
   ---
   layout: page
   title: New Page
   permalink: /newpage/
   ---
   
   Your content here...
   ```

2. Add to navigation in `_config.yml`:
   ```yaml
   navigation:
     - title: New Page
       url: /newpage
   ```

---

## 🔍 Testing Locally (Optional)

If you want to test locally before deploying:

### Windows
1. Download Ruby from [RubyInstaller](https://rubyinstaller.org/) (Ruby 3.1+)
2. Install with DevKit
3. Open new terminal:
   ```bash
   gem install bundler
   cd C:\projects\sanddollartechnology
   bundle install
   bundle exec jekyll serve
   ```
4. Visit `http://localhost:4000`

### Mac/Linux
```bash
# Install Ruby (if needed)
# Mac: brew install ruby
# Ubuntu: sudo apt-get install ruby-full

gem install bundler
cd /path/to/sanddollartechnology
bundle install
bundle exec jekyll serve
```

---

## 📦 What's Included

✅ Modern, responsive design  
✅ Purple/gradient color scheme  
✅ Smooth animations  
✅ SEO optimized  
✅ Mobile-friendly navigation  
✅ Contact form ready  
✅ GitHub Actions auto-deployment  
✅ Fast page loads  
✅ Professional content  

---

## 🆘 Troubleshooting

### Build Fails on GitHub

Check the "Actions" tab for error details. Common issues:
- Syntax errors in YAML front matter
- Missing dependencies (should auto-install)

### Contact Form Not Working

- Verify Formspree form ID is correct
- Check that email is verified in Formspree
- Test form submission

### Custom Domain Not Working

- DNS changes take 24-48 hours to propagate
- Verify CNAME file contains only the domain (no http://)
- Check GitHub Pages settings show your custom domain

### Styles Not Loading

- Clear browser cache
- Check that `assets/css/main.scss` starts with `---` (Jekyll front matter)
- Verify all `_sass/*.scss` files exist

---

## 📞 Need Help?

- Jekyll Docs: https://jekyllrb.com/docs/
- GitHub Pages: https://docs.github.com/pages
- Formspree Help: https://help.formspree.io/

---

## 🎉 You're All Set!

Once deployed, your professional website will be live and ready to showcase Sand Dollar Technology's services!
