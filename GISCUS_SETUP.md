# Giscus Setup Guide

To complete the Giscus integration, you need to get the repository ID and category ID from GitHub. Follow these steps:

## Step 1: Enable GitHub Discussions

1. Go to your repository: https://github.com/gokeeng/engineering-blog
2. Click on **Settings** tab
3. Scroll down to the **Features** section
4. Check the box next to **Discussions** to enable it
5. Click **Set up discussions** if prompted

## Step 2: Get Giscus Configuration

1. Visit: https://giscus.app/
2. Enter your repository: `gokeeng/engineering-blog`
3. Choose **Discussion category**: "General" (or create a new one like "Blog Comments")
4. The site will generate the configuration for you

## Step 3: Update _config.yml

Copy the generated values and update your `_config.yml` file:

```yaml
giscus:
  repo: "gokeeng/engineering-blog"
  repo_id: "R_[YOUR_REPO_ID]"  # Copy from giscus.app
  category: "General"
  category_id: "DIC_[YOUR_CATEGORY_ID]"  # Copy from giscus.app
  # ... rest stays the same
```

## Step 4: Test

1. Commit and push your changes
2. Visit your blog post on GitHub Pages
3. You should see the comments section at the bottom

## Features You'll Get

- ✅ **Reactions**: Readers can react with emojis
- ✅ **Comments**: Full threaded discussions
- ✅ **GitHub Integration**: Users sign in with GitHub
- ✅ **Moderation**: You control the discussions
- ✅ **Notifications**: GitHub notifies you of new comments

## Troubleshooting

- Make sure your repository is **public**
- Ensure **Discussions** are enabled in repository settings
- The `giscus` app must be installed on your repository (it will prompt you)
