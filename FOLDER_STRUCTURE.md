# .github Repository Structure

Complete guide to this repository's organization.

## 📁 Directory Structure

```
.github/
├── profile/
│   └── README.md                   → Organization profile (visible on github.com/tayank-inc)
│
├── ISSUE_TEMPLATE/
│   ├── bug_report.yml              → Bug report template
│   ├── feature_request.yml         → Feature request template
│   └── config.yml                  → Issue template configuration
│
├── workflows/
│   ├── reusable-go-ci.yml          → Reusable Go CI workflow
│   ├── reusable-node-ci.yml        → Reusable Node.js CI workflow (future)
│   └── reusable-flutter-ci.yml     → Reusable Flutter CI workflow (future)
│
├── PULL_REQUEST_TEMPLATE.md        → Pull request template (all repos)
├── CONTRIBUTING.md                 → How to contribute
├── CODE_OF_CONDUCT.md              → Community guidelines
├── SECURITY.md                     → Security policy & vulnerability reporting
├── SETUP_GUIDE.md                  → Step-by-step guide to set up this organization-wide repository.
├── SUPPORT.md                      → Where to get help
├── LICENSE                         → MIT License
├── README.md                       → This file
└── FOLDER_STRUCTURE.md             → This structure guide
```

## 📄 File Descriptions

### profile/README.md
**Purpose:** Organization landing page on GitHub  
**Visible to:** Public (everyone visiting github.com/tayank-inc)  
**Contains:**
- Project overview
- Repository links
- Features & roadmap
- Contact information

**Usage:** Automatically displayed on organization page

---

### ISSUE_TEMPLATE/bug_report.yml
**Purpose:** Standardized bug reporting  
**Used by:** All organization repositories (unless overridden)  
**Format:** YAML form (GitHub's new issue form format)  

**Sections:**
- Description
- Steps to reproduce
- Expected vs actual behavior
- Component selection
- Severity level
- Environment details
- Logs/screenshots

---

### ISSUE_TEMPLATE/feature_request.yml
**Purpose:** Structured feature requests  
**Used by:** All organization repositories  
**Format:** YAML form

**Sections:**
- Problem statement
- Proposed solution
- Alternatives considered
- Use cases
- Mockups/examples

---

### ISSUE_TEMPLATE/config.yml
**Purpose:** Configure issue templates & external links  
**Contains:**
- Disable blank issues
- Links to documentation
- Security reporting link

---

### workflows/reusable-go-ci.yml
**Purpose:** Shared CI/CD workflow for Go services  
**Used by:** All Go microservices

**Jobs:**
1. Lint & Format (golangci-lint, gofmt)
2. Security Scan (Gosec)
3. Unit Tests (with coverage check)
4. Integration Tests (optional)
5. Build (compile binary)
6. Docker Build (on main branch)
7. Notify (status reporting)

**How to use:**
```yaml
# In service repo: .github/workflows/ci.yml
jobs:
  ci:
    uses: tayank-inc/.github/.github/workflows/reusable-go-ci.yml@main
    with:
      go-version: '1.21'
      coverage-threshold: 80
```

---

### PULL_REQUEST_TEMPLATE.md
**Purpose:** Consistent PR format across all repos  
**Used by:** All pull requests in organization  

**Sections:**
- Description & issue link
- Type of change
- Changes made
- Testing details
- Screenshots
- Checklist

---

### CONTRIBUTING.md
**Purpose:** Comprehensive contribution guide  
**Audience:** Contributors (internal & external)

**Contents:**
- How to contribute (bugs, features, code)
- Development setup
- Pull request process
- Coding standards (Go, TypeScript, Flutter)
- Commit guidelines (Conventional Commits)
- Testing guidelines

---

### CODE_OF_CONDUCT.md
**Purpose:** Community behavior standards  
**Based on:** Contributor Covenant v2.1  

**Key sections:**
- Our pledge
- Standards (expected & unacceptable behavior)
- Enforcement responsibilities
- Reporting process
- Consequences

---

### SECURITY.md
**Purpose:** Security vulnerability reporting & policies  

**Contains:**
- How to report vulnerabilities (security@tayank.com)
- Response timeline
- Severity levels (Critical → Low)
- Bug bounty program info
- Security measures implemented
- Supported versions
- Best practices for users

---

### SUPPORT.md
**Purpose:** Where to get help  

**Resources:**
- Self-service (docs, FAQ)
- Bug reports & feature requests
- Email support (different addresses)
- Social media
- Service status

---

### LICENSE
**Purpose:** Legal license for repository content  
**Type:** MIT License  
**Applies to:** .github repository content (templates, docs)

**Note:** Individual project repositories may have different licenses.

---

### README.md
**Purpose:** Overview of .github repository itself  
**Contains:**
- Repository purpose
- File descriptions
- Quick links
- How to use templates

---

## 🎯 How Files Are Used

### Automatic Application

These files apply to **all repositories** in the organization automatically:

- ✅ `ISSUE_TEMPLATE/*` - Unless repo has its own
- ✅ `PULL_REQUEST_TEMPLATE.md` - Unless repo has its own
- ✅ `CODE_OF_CONDUCT.md` - Referenced from all repos
- ✅ `SECURITY.md` - Referenced from all repos
- ✅ `CONTRIBUTING.md` - Referenced from all repos
- ✅ `SUPPORT.md` - Linked from issues/PRs

### Manual Reference

These files are used explicitly:

- 🔗 `workflows/*.yml` - Called from service repos
- 🔗 `profile/README.md` - Displayed on org page

### Repository Override

Individual repos can override these files by creating their own:

```
Example:
tayank-inc/auth-service/.github/ISSUE_TEMPLATE/bug_report.yml
  ↑ This overrides the organization template
```

## 🔄 Update Process

### When to Update

- ✏️ **Bug report template** - When fields are missing/redundant
- ✏️ **Feature template** - When request format changes
- ✏️ **PR template** - When checklist items change
- ✏️ **Contributing** - When development process changes
- ✏️ **Security** - When contact/policy changes
- ✏️ **Workflows** - When CI/CD process improves

### How to Update

1. Create branch: `update/template-name`
2. Make changes
3. Test with a service repo
4. Open PR (requires 1 approval)
5. Merge to main
6. Changes apply organization-wide

### Testing Templates

Before merging template changes:

```bash
# Create test issue/PR in a sandbox repo
# Use the updated template
# Verify all fields work
# Check for typos/formatting
```

## 📋 Checklist for New Files

When adding new files:

- [ ] Add description to this FOLDER_STRUCTURE.md
- [ ] Update README.md if necessary
- [ ] Test in at least one repository
- [ ] Document usage in CONTRIBUTING.md if applicable

## 🔗 Related Resources

- [GitHub Docs: Creating a default community health file](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
- [GitHub Docs: Issue and PR templates](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests)
- [GitHub Docs: Reusable workflows](https://docs.github.com/en/actions/using-workflows/reusing-workflows)

---

**Questions?** Open a [Discussion](https://github.com/orgs/tayank-inc/discussions)