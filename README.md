

# 🚀 Static Site Deployment with GitHub Pages

This repo demonstrates deploying a static HTML website using **GitHub Actions** and **GitHub Pages**.

---

## ⚙️ GitHub Actions Workflow

Create a file at `.github/workflows/deploy.yml` with the following content:

### `deploy.yml`

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches:
      - main  # Trigger on push to main branch

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./  
```

---

# Required Settings
    Grant Write Access to Actions
    Go to:
        Settings > Actions > General > Workflow Permissions

    Select "Read and write permissions" and Save

# Enable GitHub Pages
    Go to Settings > Pages in your repo.

    Set:

    Source: Deploy from a branch

    Branch: gh-pages

    Folder: / (root)

    Click Save.

# After Setup
    On every push to main, GitHub will:

    Build and deploy your site.

    Host it at:
    https://<username>.github.io/<repo-name>/


