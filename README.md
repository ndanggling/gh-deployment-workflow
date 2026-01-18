# GitHub Actions Deployment Workflow

A simple demonstration of CI/CD using GitHub Actions to automatically deploy a static website to GitHub Pages.

## 🚀 Live Demo

Visit the deployed site: `https://<username>.github.io/github-actions-deployment-workflow/`

## 📋 Overview

This project demonstrates the fundamentals of Continuous Integration and Continuous Deployment (CI/CD) using GitHub Actions. The workflow automatically deploys changes to GitHub Pages whenever the `index.html` file is modified.

## ✨ Features

- **Automatic Deployment**: Changes to `index.html` trigger automatic deployment
- **Conditional Triggers**: Workflow only runs when `index.html` is modified (not on README or other file changes)
- **GitHub Pages Integration**: Uses official GitHub Actions for seamless Pages deployment
- **Zero Configuration**: No external services or API keys required

## 📁 Project Structure

```
github-actions-deployment-workflow/
├── .github/
│   └── workflows/
│       └── deploy.yml    # GitHub Actions workflow
├── index.html            # Static website
└── README.md             # Project documentation
```

## 🔧 How It Works

1. **Push to Main Branch**: When you push changes to the `main` branch
2. **Path Filter**: GitHub Actions checks if `index.html` was modified
3. **Workflow Trigger**: If `index.html` changed, the deployment workflow runs
4. **Build & Deploy**: The workflow uploads the site to GitHub Pages
5. **Live Update**: Your changes are live at the GitHub Pages URL

### Workflow Configuration

The workflow uses the `paths` filter to only trigger on specific file changes:

```yaml
on:
  push:
    branches:
      - main
    paths:
      - 'index.html'  # Only triggers when index.html is modified
```

## 🛠️ Setup Instructions

### 1. Fork or Clone This Repository

```bash
git clone https://github.com/<username>/github-actions-deployment-workflow.git
cd github-actions-deployment-workflow
```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Pages**
3. Under "Build and deployment", select **GitHub Actions** as the source
4. Save the settings

### 3. Push Changes

```bash
git add .
git commit -m "Initial commit"
git push origin main
```

### 4. Verify Deployment

1. Go to the **Actions** tab in your repository
2. Watch the workflow run
3. Once complete, visit your GitHub Pages URL

## 🧪 Testing the Workflow

### Test 1: Modify index.html (Should Trigger Deployment)

```bash
# Edit index.html
echo "<!-- Updated -->" >> index.html
git add index.html
git commit -m "Update index.html"
git push
```

✅ Expected: Workflow runs and deploys

### Test 2: Modify README.md (Should NOT Trigger Deployment)

```bash
# Edit README.md
echo "<!-- Updated -->" >> README.md
git add README.md
git commit -m "Update README"
git push
```

❌ Expected: Workflow does NOT run

## 📚 Learning Outcomes

After completing this project, you will understand:

- **GitHub Actions**: How to create and configure workflows
- **GitHub Pages**: How to deploy static sites for free
- **CI/CD Concepts**: Continuous Integration and Continuous Deployment principles
- **YAML Configuration**: Writing workflow configuration files
- **Path Filters**: Triggering workflows based on specific file changes

## 🔗 Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Roadmap.sh Project](https://roadmap.sh/projects/github-actions-deployment-workflow)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
