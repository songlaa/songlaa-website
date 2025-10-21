# songlaa.com

## 🖥️ Local Development

### Prerequisites
- Docker (recommended) or Hugo installed locally

### Using Docker (Recommended)

```bash
# Clone the repository
git clone <repository-url>
cd songlaa.com

# Start the development server using Docker
docker run --rm -it -v $(pwd):/src -p 1313:1313 klakegg/hugo:alpine server --bind 0.0.0.0

# The site will be available at http://localhost:1313/
```

## 🔧 Theme Management

### Current Theme
This site uses the **hugo-elate** theme, which provides:
- Single-page scrolling design
- Modern animations and transitions
- Responsive Bootstrap-based layout
- Professional business presentation

### Updating the Theme

If you need to update or modify the hugo-elate theme:

1. **Theme location**: `themes/hugo-elate/`
2. **Custom partials**: Training sections are in `themes/hugo-elate/layouts/partials/`
   - `kubernetes-fundamentals.html`
   - `kubernetes-security.html` 
   - `cilium.html`

3. **To update theme files**:
   ```bash
   # Backup current customizations
   git checkout -b theme-update-backup
   
   # Make your changes to theme files
   # Test thoroughly with docker/hugo server
   
   # Commit changes
   git add .
   git commit -m "feat: update theme customizations"
   ```

### Configuration Files

- **Main config**: `config/_default/hugo.toml`
- **Parameters**: `config/_default/params.toml` (contains training content and styling)
- **Menus**: `config/_default/menus.en.toml`
- **Languages**: `config/_default/languages.toml`

### Content Management

Training content is managed in `config/_default/params.toml` under these sections:
- `[kubernetes_fundamentals]`
- `[kubernetes_security]` 
- `[cilium]`

To update training information, modify the content in these sections and restart the development server.

## � Building for Production

```bash
# Using Docker
docker run --rm -it -v $(pwd):/src klakegg/hugo:alpine

# Using local Hugo
hugo --minify
```

The built site will be in the `public/` directory.

## � Project Structure

```
songlaa.com/
├── config/_default/          # Hugo configuration files
├── content/english/          # Content files (mostly unused due to single-page design)
├── themes/hugo-elate/        # Hugo Elate theme with customizations
│   ├── layouts/partials/     # Custom training section templates
│   └── static/              # Theme assets (CSS, JS, images)
├── static/                   # Site-specific static files
└── public/                   # Generated site (created during build)
```

## � Acknowledgments

- [Hugo Elate Theme](https://github.com/saey55/hugo-elate-theme) by saey55
- [Hugo Static Site Generator](https://gohugo.io/)
- [Bootstrap Framework](https://getbootstrap.com)
- Original theme based on [FREEHTML5.co](http://freehtml5.co/) template

## � Contact

For training inquiries or website questions, please visit the contact section on the website or reach out through our LinkedIn profile.

---

**Built with ❤️ for the Kubernetes community**
