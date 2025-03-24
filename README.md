# Iamneo
.github/workflows/deploy.yml
name: 🚀 Auto Deploy Website

on:
  push:
    branches:
      - main  # Deploy when pushing to the 'main' branch

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v3

      - name: Deploy to GitHub Pages
        run: |
          git config --global user.name "ahmedmohammed8694"
          git config --global user.email "ahmed.mohammed8694@gmail.com"
          git remote set-url origin https://x-access-token:${{ secrets.GITHUB_PAT }}@github.com/ahmedmohammed8694/iamneo-website.git
          git add .
          git commit -m "Auto-deploying site update"
          git push origin main
