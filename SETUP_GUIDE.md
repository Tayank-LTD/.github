# .github Repository Setup Guide

Step-by-step guide to set up this organization-wide repository.

## 📋 Prerequisites

- ✅ GitHub Organization created (`tayank-inc`)
- ✅ Admin access to the organization
- ✅ Basic Git knowledge

## 🚀 Initial Setup

### Step 1: Create Repository

```bash
# Via GitHub CLI
gh repo create tayank-inc/.github --public

# Or via Web UI:
# 1. Go to https://github.com/organizations/tayank-inc/repositories/new
# 2. Repository name: .github
# 3. Description: Organization-wide files and templates
# 4. Visibility: Public
# 5. Click "Create repository"
```

### Step 2: Clone Repository

```bash
git clone https://github.com/tayank-inc/.github.git
cd .github
```

### Step 3: Create Folder Structure

```bash
# Create all necessary folders
mkdir -p profile
mkdir -p ISSUE_TEMPLATE
mkdir -p workflows

# Verify structure
tree
# Should show:
# .github/
# ├── profile/
# ├── ISSUE_TEMPLATE/
# └── workflows/
```

## 📁 Adding Files

### Method 1: Manual Creation (Recommended for Learning)

Create each file one by one:

```bash
# 1. Profile README
touch profile/README.md
# Copy content from artifact

# 2. Issue templates
touch ISSUE_TEMPLATE/bug_report.yml
touch ISSUE_TEMPLATE/feature_request.yml
touch ISSUE_TEMPLATE/config.yml

# 3. PR template
touch PULL_REQUEST_TEMPLATE.md

# 4. Documentation files
touch CONTRIBUTING.md
touch CODE_OF_CONDUCT.md
touch SECURITY.md
touch SUPPORT.md

# 5. Other files
touch LICENSE
touch README.md
touch FOLDER_STRUCTURE.md
touch SETUP_GUIDE.md

# 6. Workflows
touch workflows/reusable-go-ci.yml
```

### Method 2: Bulk Creation (Faster)

Use the provided script:

```bash
# Create setup script
cat > setup.sh << 'EOF'
#!/bin/bash

# Create folders
mkdir -p profile ISSUE_TEMPLATE workflows

# Create all files
touch profile/README.md
touch ISSUE_TEMPLATE/bug_report.yml
touch ISSUE_TEMPLATE/feature_request.yml
touch ISSUE_TEMPLATE/config.yml
touch PULL_REQUEST_TEMPLATE.md
touch CONTRIBUTING.md
touch CODE_OF_CONDUCT.md
touch SECURITY.md
touch SUPPORT.md
touch LICENSE
touch README.md
touch FOLDER_STRUCTURE.md
touch SETUP_GUIDE.md
touch workflows/reusable-go-ci.yml

echo "✅ All files created!"
EOF

chmod +x setup.sh
./setup.sh
```

### Method 3: Using Artifacts (Easiest)

1. Download all artifacts from this conversation
2. Place files in correct folders:
   ```
   profile/README.md
   ISSUE_TEMPLATE/bug_report.yml
   ISSUE_TEMPLATE/feature_request.yml
   ISSUE_TEMPLATE/config.yml
   PULL_REQUEST_TEMPLATE.md
   CONTRIBUTING.md
   CODE_OF_CONDUCT.md
   SECURITY.md
   SUPPORT.md
   LICENSE
   README.md
   FOLDER_STRUCTURE.md
   SETUP_GUIDE.md
   workflows/reusable-go-ci.yml
   ```

## ✏️ Customization

### Essential Customizations

Before committing, update these placeholders:

#### 1. Email Addresses

**Files to update:**
- `SECURITY.md` - security@tayank.com
- `SUPPORT.md` - support@tayank.com, business@tayank.com, press@tayank.com
- `CONTRIBUTING.md` - contribute@tayank.com
- `CODE_OF_CONDUCT.md` - conduct@tayank.com

**Find & Replace:**
```bash
# Replace with your actual emails
find . -type f -exec sed -i 's/security@tayank.com/your-security-email@example.com/g' {} +
find . -type f -exec sed -i 's/support@tayank.com/your-support-email@example.com/g' {} +
# ... repeat for other emails
```

#### 2. Links

**Files to update:**
- `profile/README.md` - All GitHub links
- `SUPPORT.md` - Social media links
- `CONTRIBUTING.md` - Documentation links

**Update these:**
- `https://tayank.com` → Your website
- `https://docs.tayank.com` → Your docs site
- `https://twitter.com/tayankapp` → Your Twitter

#### 3. Organization Name

If you're not using "Tayank":

```bash
# Replace organization name
find . -type f -exec sed -i 's/Tayank/YourName/g' {} +
find . -type f -exec sed -i 's/tayank-inc/your-org/g' {} +
```

#### 4. License

If not using MIT License:

```bash
# Replace LICENSE file with your preferred license
# Examples:
# - Apache 2.0
# - GPL v3
# - BSD 3-Clause
```

### Optional Customizations

#### Add Organization Logo

```bash
# Add logo to profile folder
mkdir -p profile/assets
# Place logo.png (200x200px recommended)

# Update profile/README.md to reference it:
# <img src="https://raw.githubusercontent.com/your-org/.github/main/profile/assets/logo.png" ...>
```

#### Add More Workflows

```bash
# Add Node.js workflow
touch workflows/reusable-node-ci.yml

# Add Flutter workflow
touch workflows/reusable-flutter-ci.yml

# Add Docker build workflow
touch workflows/reusable-docker-build.yml
```

## 📤 Commit & Push

### Initial Commit

```bash
# Stage all files
git add .

# Commit
git commit -m "Initial setup: organization-wide templates and docs

- Add profile README
- Add issue templates (bug, feature)
- Add PR template
- Add contributing guide
- Add code of conduct
- Add security policy
- Add support guide
- Add reusable Go CI workflow
- Add LICENSE (MIT)
"

# Push to main
git push origin main
```

### Branch Protection (Recommended)

```bash
# Via GitHub CLI
gh api repos/tayank-inc/.github/branches/main/protection \
  --method PUT \
  --field required_status_checks='{"strict":true,"contexts":[]}' \
  --field enforce_admins=true \
  --field required_pull_request_reviews='{"required_approving_review_count":1}' \
  --field restrictions=null

# Or via Web UI:
# Settings → Branches → Add rule → main
# ☑ Require pull request before merging
# ☑ Require approvals: 1
```

## ✅ Verification

### Test Templates

#### 1. Test Issue Templates

Go to any repository in your organization:

```
https://github.com/tayank-inc/ANY-REPO/issues/new/choose
```

You should see:
- 🐛 Bug Report
- ✨ Feature Request

#### 2. Test PR Template

Create a test PR in any repo. The template should auto-populate.

#### 3. Test Profile Page

Visit:
```
https://github.com/tayank-inc
```

Your profile README should be visible.

### Verify Workflow

Test the reusable workflow in a service repo:

```yaml
# service-repo/.github/workflows/ci.yml
name: CI

on: [push, pull_request]

jobs:
  test:
    uses: tayank-inc/.github/.github/workflows/reusable-go-ci.yml@main
    with:
      go-version: '1.21'
      coverage-threshold: 80
```

## 🔄 Maintenance

### Regular Updates

**Monthly:**
- [ ] Review and update links (check for 404s)
- [ ] Update contact emails if changed
- [ ] Review security policy

**Quarterly:**
- [ ] Update dependencies in workflows
- [ ] Review and improve templates based on feedback
- [ ] Add new resources/links

**Yearly:**
- [ ] Update copyright year in LICENSE
- [ ] Review and update contribution guidelines
- [ ] Update roadmap in profile README

### Monitoring

Track template usage:

```bash
# See which repos are using templates
gh api orgs/tayank-inc/repos --paginate \
  | jq -r '.[] | select(.has_issues == true) | .name'

# Check workflow usage
gh api /orgs/tayank-inc/actions/secrets
```

## 🐛 Troubleshooting

### Templates Not Showing

**Problem:** Issue templates not appearing in repositories

**Solutions:**
1. Check repository visibility (templates apply to public repos)
2. Clear browser cache
3. Wait 5-10 minutes (GitHub cache)
4. Verify file paths are correct

### Profile Not Visible

**Problem:** Organization profile README not showing

**Solutions:**
1. Ensure `.github` repo is public
2. File must be at `profile/README.md` (exact path)
3. Clear cache and refresh

### Workflows Not Working

**Problem:** Reusable workflows not found

**Solutions:**
1. Check workflow file path: `.github/workflows/name.yml`
2. Ensure `.github` repo is public (or same visibility)
3. Verify workflow syntax (YAML validation)
4. Check workflow permissions in organization settings

## 📚 Next Steps

After setup:

1. **Create Service Repos** - Start creating actual service repositories
2. **Test Integration** - Verify templates work in real repos
3. **Team Training** - Teach team how to use templates
4. **Documentation** - Link to this repo from main project docs
5. **Iterate** - Improve based on feedback

## 📞 Help & Support

- 📖 [GitHub Docs](https://docs.github.com/en/communities)
- 📧 Email: devops@tayank.com

---

**Setup complete?** Star this repo and start building! 🚀