# Public Beta Repo Setup Instructions

Follow these steps to create and configure the public beta repository.

## Step 1: Create Public GitHub Repository

1. Go to GitHub: https://github.com/new
2. Repository name: **SketchAcoustics-Beta**
3. Description: **Public releases for SketchAcoustics beta testing**
4. Visibility: **✅ Public**
5. Initialize: **❌ DO NOT** check "Add a README" (we have one)
6. Click **Create repository**

## Step 2: Push Initial Files

```bash
# Navigate to the beta repo folder
cd /Users/vladimiras/Developer/SketchAcoustics-Beta

# Initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial beta repo setup"

# Add remote (replace YOUR_USERNAME with your GitHub username)
git remote add origin https://github.com/YOUR_USERNAME/SketchAcoustics-Beta.git

# Push
git branch -M main
git push -u origin main
```

## Step 3: Create GitHub Personal Access Token (PAT)

This allows the private repo workflow to push releases to the public repo.

1. Go to GitHub Settings: https://github.com/settings/tokens
2. Click **"Developer settings"** (bottom left)
3. Click **"Personal access tokens"** → **"Tokens (classic)"**
4. Click **"Generate new token (classic)"**
5. Fill in:
   - **Note**: `SketchAcoustics Beta Release Automation`
   - **Expiration**: `No expiration` (or custom, e.g., 1 year)
   - **Scopes**: ✅ Check **`repo`** (full control of private repositories)
6. Click **"Generate token"**
7. **⚠️ COPY THE TOKEN** - You won't see it again!

## Step 4: Add PAT to Private Repo Secrets

1. Go to your **private** repo: https://github.com/YOUR_USERNAME/SketchAcoustics-Suite
2. Click **Settings** → **Secrets and variables** → **Actions**
3. Click **"New repository secret"**
4. Fill in:
   - **Name**: `BETA_REPO_PAT`
   - **Secret**: (paste the PAT token from Step 3)
5. Click **"Add secret"**

## Step 5: Verify Setup

To verify everything is configured correctly:

1. The public repo should exist: `https://github.com/YOUR_USERNAME/SketchAcoustics-Beta`
2. It should have these files:
   - README.md
   - CHANGELOG.md
   - .gitignore
3. The private repo should have:
   - Secret named `BETA_REPO_PAT` configured
   - Updated `.github/workflows/release.yml` workflow

## Step 6: Test Release (Optional)

Once the workflow is updated, test it:

1. Go to your **private** repo
2. Click **Actions** → **"Build and Release Beta"**
3. Click **"Run workflow"**
4. Enter:
   - Version: `0.1.0-beta.1`
   - Changelog: `Initial beta release with first reflections calculator`
5. Click **"Run workflow"**
6. Wait for completion (~1-2 minutes)
7. Check both repos for releases:
   - Private: https://github.com/YOUR_USERNAME/SketchAcoustics-Suite/releases
   - Public: https://github.com/YOUR_USERNAME/SketchAcoustics-Beta/releases

---

## Troubleshooting

### "Resource not accessible by integration"
- Make sure `BETA_REPO_PAT` secret is set correctly
- Verify the PAT has `repo` scope

### "Remote not found"
- Check the repository name matches exactly: `SketchAcoustics-Beta`
- Verify the workflow uses the correct repository owner name

### Workflow fails at "Update public repo CHANGELOG"
- Make sure CHANGELOG.md exists in the public repo
- Check the public repo is accessible

---

## Next Steps

After setup is complete, you can:
1. Invite beta testers by sharing: `https://github.com/YOUR_USERNAME/SketchAcoustics-Beta`
2. Release new versions via GitHub Actions workflow
3. Monitor downloads and feedback

Need help? Check the main repo documentation or reach out!
