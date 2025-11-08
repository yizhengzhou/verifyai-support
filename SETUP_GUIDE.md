# GitHub Pages Setup Guide for VerifyAI

This guide will help you enable GitHub Pages and get your support website live for Apple Connect review.

## Step 1: Merge the Branch to Main

First, you need to merge this branch into your main branch:

1. Go to GitHub and create a Pull Request from this branch
2. Review the changes
3. Merge the PR into your main branch

OR use command line:
```bash
git checkout main
git merge claude/appleconnect-review-urls-011CUukMGNgRW5Nin431J9Ph
git push origin main
```

## Step 2: Enable GitHub Pages

1. Go to your GitHub repository: `https://github.com/yizhengzhou/image-fact-check`
2. Click on **Settings** (top navigation)
3. Scroll down to **Pages** section (in left sidebar under "Code and automation")
4. Under **Source**, select:
   - **Branch:** `main`
   - **Folder:** `/website` (or `/` and then navigate to website)
5. Click **Save**

## Step 3: Wait for Deployment

GitHub Pages will take 1-2 minutes to build and deploy your site. You'll see a message like:

> "Your site is ready to be published at `https://yizhengzhou.github.io/image-fact-check/`"

## Step 4: Get Your Support URL

Once deployed, your support URL will be:

**For Apple Connect Review**, use one of these:

- **English Support Page:**
  ```
  https://yizhengzhou.github.io/image-fact-check/website/support.html
  ```

- **Chinese Support Page:**
  ```
  https://yizhengzhou.github.io/image-fact-check/website/support-zh.html
  ```

- **Homepage (if they want to see app info):**
  ```
  https://yizhengzhou.github.io/image-fact-check/website/index.html
  ```

## Step 5: Test Your Website

Before submitting to Apple:

1. Visit the URL in your browser
2. Check all pages load correctly:
   - Homepage (index.html)
   - Support (support.html)
   - User Guide (user-guide.html)
   - Privacy Policy (privacy-policy-en.html)
3. Test on mobile to ensure responsive design works
4. Verify all links work correctly
5. Confirm your email (yizheng@fork.work) appears correctly

## Step 6: Update Apple Connect

1. Log in to App Store Connect
2. Go to your app's **App Information**
3. Update the **Support URL** field with:
   ```
   https://yizhengzhou.github.io/image-fact-check/website/support.html
   ```
4. Save changes

## Optional: Custom Domain

If you want to use a custom domain (e.g., `verifyai.com` or `support.verifyai.com`):

1. Purchase a domain from a domain registrar
2. In your domain's DNS settings, add a CNAME record:
   - Name: `www` (or subdomain like `support`)
   - Value: `yizhengzhou.github.io`
3. In GitHub Pages settings, add your custom domain
4. Wait for DNS propagation (up to 24 hours)

## Troubleshooting

### Issue: 404 Not Found

- Make sure you selected the correct branch and folder
- Wait a few minutes for GitHub to rebuild
- Clear your browser cache

### Issue: CSS Not Loading

- Check that the `.nojekyll` file exists in the website directory
- Verify the CSS path in HTML files is correct: `assets/css/style.css`

### Issue: Images Missing (if you add any later)

- Make sure image paths are relative: `assets/images/logo.png`
- Don't use absolute paths starting with `/`

## File Structure

```
website/
├── .nojekyll                   # Tells GitHub not to use Jekyll
├── README.md                   # Website documentation
├── SETUP_GUIDE.md             # This file
├── index.html                 # English homepage
├── index-zh.html              # Chinese homepage
├── support.html               # English support (USE THIS FOR APPLE)
├── support-zh.html            # Chinese support
├── user-guide.html            # English user guide
├── user-guide-zh.html         # Chinese user guide
├── privacy-policy-en.html     # English privacy policy
├── privacy-policy-zh.html     # Chinese privacy policy
└── assets/
    └── css/
        └── style.css          # Stylesheet
```

## Updating Content Later

To update the website content:

1. Edit the HTML files directly in the `website/` directory
2. Commit and push changes:
   ```bash
   git add website/
   git commit -m "Update support website content"
   git push origin main
   ```
3. GitHub Pages will automatically rebuild (takes 1-2 minutes)

## Support

If you encounter any issues:
- Check GitHub Pages documentation: https://docs.github.com/en/pages
- Verify your repository is public (or you have GitHub Pro for private repos)
- Make sure GitHub Actions have permission to deploy

---

**Your Support URL for Apple Connect:**
```
https://yizhengzhou.github.io/image-fact-check/website/support.html
```

Copy this URL and paste it into App Store Connect's "Support URL" field.
