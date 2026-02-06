# Sand Dollar Technology Website - Setup Guide

This is a professional Jekyll website for Sand Dollar Technology. The site features a modern design with purple/gradient accents and is optimized for GitHub Pages deployment.

## Quick Start (GitHub Pages - Recommended)

The easiest way to get this site running is through GitHub Pages with automated deployment:

1. **Create a GitHub repository**
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Sand Dollar Technology website"
   git remote add origin https://github.com/YOUR_USERNAME/sanddollartechnology.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository settings
   - Navigate to "Pages" section
   - Under "Build and deployment", select "GitHub Actions" as the source
   - The site will automatically build and deploy on every push

3. **Access your site**
   - Your site will be available at: `https://YOUR_USERNAME.github.io/sanddollartechnology/`
   - Or configure a custom domain in the repository settings

## Local Development

To run the site locally, you need Ruby and Jekyll installed:

### Prerequisites

1. **Install Ruby** (version 2.7 or higher)
   - **Windows**: Download from [RubyInstaller](https://rubyinstaller.org/)
   - **Mac**: Ruby comes pre-installed, or use `brew install ruby`
   - **Linux**: `sudo apt-get install ruby-full` (Ubuntu/Debian)

2. **Install Bundler**
   ```bash
   gem install bundler
   ```

### Running Locally

1. **Install dependencies**
   ```bash
   cd C:\projects\sanddollartechnology
   bundle install
   ```

2. **Start the development server**
   ```bash
   bundle exec jekyll serve
   ```

3. **View the site**
   - Open your browser to `http://localhost:4000`
   - The site will auto-reload when you make changes

## Configuration

### Update Site Settings

Edit `_config.yml` to customize:
- Site title and description
- Email and social media links
- Base URL (if using a custom domain)
- Navigation menu items

### Contact Form Setup

The contact form uses Formspree. To enable it:

1. Sign up at [Formspree.io](https://formspree.io)
2. Create a new form
3. Copy your form ID
4. Update `contact.md` and replace `YOUR_FORM_ID` with your actual form ID:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

### Custom Domain (Optional)

To use a custom domain like `www.sanddollartechnology.com`:

1. Add a `CNAME` file to the root with your domain:
   ```
   www.sanddollartechnology.com
   ```

2. Configure DNS records with your domain provider:
   - Type: CNAME
   - Name: www (or @)
   - Value: YOUR_USERNAME.github.io

3. Update `_config.yml`:
   ```yaml
   url: "https://www.sanddollartechnology.com"
   baseurl: ""
   ```

## Site Structure

```
sanddollartechnology/
├── _config.yml           # Site configuration
├── _layouts/             # Page templates
│   ├── default.html      # Main layout with header/footer
│   └── page.html         # Standard page layout
├── _includes/            # Reusable components
│   ├── header.html       # Site navigation
│   └── footer.html       # Site footer
├── _sass/                # Stylesheets
│   ├── _variables.scss   # Colors, fonts, spacing
│   ├── _base.scss        # Base styles
│   ├── _components.scss  # Component styles
│   └── _animations.scss  # Animations
├── assets/
│   ├── css/
│   │   └── main.scss     # Main stylesheet
│   ├── js/
│   │   └── main.js       # JavaScript
│   └── images/           # Images and icons
├── index.html            # Home page
├── about.md              # About page
├── services.md           # Services page
├── contact.md            # Contact page
├── Gemfile               # Ruby dependencies
└── .github/
    └── workflows/
        └── jekyll.yml    # GitHub Actions deployment
```

## Customization

### Adding Pages

Create a new `.md` or `.html` file in the root directory:

```markdown
---
layout: page
title: Your Page Title
permalink: /your-page/
---

Your content here...
```

Then add it to the navigation in `_config.yml`:

```yaml
navigation:
  - title: Your Page
    url: /your-page
```

### Styling

All styles are in `_sass/` directory:
- Modify colors in `_variables.scss`
- Add components in `_components.scss`
- Adjust base styles in `_base.scss`

### Adding Images

Place images in `assets/images/` and reference them:

```markdown
![Alt text]({{ '/assets/images/your-image.jpg' | relative_url }})
```

## Deployment Checklist

Before going live:

- [ ] Update `_config.yml` with your actual details
- [ ] Replace placeholder social media links
- [ ] Set up Formspree for the contact form
- [ ] Add your own images/logo
- [ ] Test all links and forms
- [ ] Review content for accuracy
- [ ] Set up custom domain (if applicable)
- [ ] Enable HTTPS in GitHub Pages settings

## Maintenance

### Updating Content

Simply edit the markdown files and push to GitHub. The site will automatically rebuild and deploy.

### Updating Dependencies

Occasionally update Jekyll and plugins:

```bash
bundle update
git add Gemfile.lock
git commit -m "Update dependencies"
git push
```

## Support

For issues or questions:
- Jekyll Documentation: https://jekyllrb.com/docs/
- GitHub Pages: https://docs.github.com/pages
- Formspree: https://help.formspree.io/

## License

This website template is provided as-is for Sand Dollar Technology.
