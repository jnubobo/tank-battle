# GitHub Deployment Guide

Follow these steps to upload your Tank Battle Game to GitHub:

## Option 1: Using GitHub CLI (Recommended)

1. Install GitHub CLI from https://cli.github.com/
2. Authenticate with GitHub:
   ```bash
   gh auth login
   ```
3. Create a new repository on GitHub:
   ```bash
   gh repo create tank-battle --public --source=. --remote=origin --push
   ```

## Option 2: Using Git Commands Manually

### Step 1: Create Repository on GitHub
1. Go to https://github.com/new
2. Repository name: `tank-battle`
3. Description: "A modern HTML5 tank battle game with vanilla JavaScript"
4. Choose **Public** visibility
5. **DO NOT** initialize with README, .gitignore, or license (we already have them)
6. Click "Create repository"

### Step 2: Connect Local Repository to GitHub
```bash
# Add the remote repository
git remote add origin https://github.com/YOUR_USERNAME/tank-battle.git

# Verify the remote
git remote -v
```

### Step 3: Push Your Code
```bash
# Push to GitHub
git push -u origin master
```

## Option 3: Using GitHub Desktop

1. Download GitHub Desktop from https://desktop.github.com/
2. Install and sign in with your GitHub account
3. Click "Add Local Repository"
4. Navigate to your `tank-battle` folder
5. Click "Publish repository"
6. Fill in repository details and click "Publish"

## Verification

After pushing, visit your repository at:
```
https://github.com/YOUR_USERNAME/tank-battle
```

## Enable GitHub Pages (Optional)

To host your game for free on GitHub Pages:

1. Go to your repository on GitHub
2. Click "Settings" → "Pages"
3. Under "Source", select "Deploy from a branch"
4. Choose "master" branch and "/ (root)" folder
5. Click "Save"
6. Your game will be available at:
   ```
   https://YOUR_USERNAME.github.io/tank-battle/
   ```

## Next Steps

1. **Update README.md**: Replace `[your-username]` with your actual GitHub username
2. **Add screenshot**: Take a screenshot of the game and save as `screenshot.png`
3. **Test the game**: Open `index.html` in a browser to ensure everything works
4. **Share your game**: Share the GitHub Pages link with friends!

## Troubleshooting

### Authentication Issues
If you get authentication errors:
```bash
# Use SSH instead of HTTPS
git remote set-url origin git@github.com:YOUR_USERNAME/tank-battle.git

# Or use a personal access token
git remote set-url origin https://TOKEN@github.com/YOUR_USERNAME/tank-battle.git
```

### Push Rejected
If push is rejected because of unrelated histories:
```bash
git pull origin master --allow-unrelated-histories
git push -u origin master
```

### File Too Large
If you have large files:
```bash
# Remove large files
git rm --cached large-file.ext

# Commit and push
git commit -m "Remove large file"
git push
```