# Backcountry Hunt Training Plan - GitHub Synced

A single-page training plan tracker that syncs checkbox state across devices using a JSON file in this repo, updated via the GitHub API.

## Setup Instructions

### 1. Create a GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name it something like `hunt-training-plan`
3. Set it to **Public** (required for free GitHub Pages hosting)
4. Do NOT initialize with README (you'll push these files instead)

### 2. Upload Files

Push the contents of this folder to your new repo:

```bash
cd /path/to/these/files
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/hunt-training-plan.git
git push -u origin main
```

The file structure should be:
```
/
├── index.html
├── state/
│   └── checkboxes.json
└── README.md
```

### 3. Enable GitHub Pages

1. Go to your repo on GitHub
2. **Settings** > **Pages** (left sidebar)
3. Source: **Deploy from a branch**
4. Branch: **main** / root
5. Click **Save**
6. Wait 1-2 minutes for deployment
7. Your site will be at: `https://YOUR_USERNAME.github.io/hunt-training-plan/`

### 4. Create a Personal Access Token (PAT)

1. Go to [GitHub Settings > Developer Settings > Fine-grained tokens](https://github.com/settings/personal-access-tokens/new)
2. Click **Generate new token**
3. Name: `Hunt Plan Sync` (or whatever you like)
4. Expiration: Set to your preference (90 days, or custom past hunt season)
5. **Repository access**: Select **Only select repositories** > choose your training plan repo
6. **Permissions**: Under "Repository permissions", set **Contents** to **Read and write**
7. Click **Generate token**
8. **Copy the token immediately** (you won't see it again)

### 5. Configure the Page

1. Open your published GitHub Pages URL
2. A config modal will appear on first visit
3. Enter:
   - **Owner**: Your GitHub username
   - **Repo**: The repository name (e.g., `hunt-training-plan`)
   - **Branch**: `main` (default)
   - **PAT**: Paste your token
4. Click **Test Connection** to verify
5. Click **Save**

Your checkboxes will now sync to `state/checkboxes.json` in your repo.

## How It Works

- Checkbox state is stored as JSON in `state/checkboxes.json`
- When you check/uncheck a box, the page pushes an update to GitHub via the Contents API
- Changes are debounced (waits 1 second after your last click before pushing)
- On load, the page fetches the latest state from GitHub
- If GitHub is unreachable, it falls back to localStorage (offline mode)

## Multi-Device Sync

Open the page on any device, enter the same config, and your progress stays in sync. The JSON file in the repo is the single source of truth.

## Security Notes

- Your PAT is stored **only in your browser's localStorage**
- It is **never** sent anywhere except directly to GitHub's API (`api.github.com`)
- The PAT is **not** stored in any file in this repo
- Each device/browser needs its own config entry
- Use a fine-grained token with minimal permissions (Contents read/write on a single repo)
- If you clear your browser data, you'll need to re-enter the config

## Reconfiguring

Click the **Settings** gear icon in the green status bar at the top of the page to update your GitHub connection settings at any time.

## Troubleshooting

| Issue | Fix |
|-------|-----|
| "Invalid token" error | Generate a new PAT; the old one may have expired |
| "File not found" error | Ensure `state/checkboxes.json` exists in your repo on the correct branch |
| "Push failed: 409" | Another device updated simultaneously; the page will auto-retry |
| Offline mode showing | Check internet connection; verify PAT hasn't expired |
| Changes not appearing on other device | Refresh the page on the other device to pull latest state |
