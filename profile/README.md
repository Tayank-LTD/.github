<div align="center">

<img src="https://raw.githubusercontent.com/tayank-inc/.github/main/profile/logo.png" alt="Tayank Logo" width="200"/>

# 🚀 Tayank

### Discord + Slack Hybrid Communication Platform

**Modern, scalable, and feature-rich communication for teams and communities**

[![Website](https://img.shields.io/badge/Website-tayank.com-blue?style=for-the-badge)](https://tayank.com)
[![Docs](https://img.shields.io/badge/Docs-docs.tayank.com-green?style=for-the-badge)](https://docs.tayank.com)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

</div>

---

## 💡 What is Tayank?

Tayank combines the best of **Discord** (gaming, community) and **Slack** (business, productivity) into one powerful platform:

- 🎮 **Gaming-first** - Low latency voice, rich presence, game integrations
- 💼 **Business-ready** - Workspaces, threads, integrations, project management
- 🔒 **Privacy-focused** - End-to-end encryption for DMs
- ⚡ **High performance** - Built with Go, optimized for 1M+ concurrent users
- 🌍 **Open ecosystem** - Public SDKs, bot platform, extensive APIs

---

## 🏗️ Architecture

Tayank uses a **microservices architecture** with:

- **Backend**: Go (11 microservices)
- **Frontend**: Next.js 15 + React
- **Mobile**: Flutter
- **Infrastructure**: Kubernetes, PostgreSQL, Redis, Kafka

---

## 📦 Projects

### 🔧 Backend Services

| Service | Description | Status |
|---------|-------------|--------|
| [auth-service](https://github.com/tayank-inc/auth-service) | Authentication & authorization | 🚧 In Development |
| [messaging-service](https://github.com/tayank-inc/messaging-service) | Real-time messaging | 🚧 In Development |
| [voice-service](https://github.com/tayank-inc/voice-service) | Voice & video calls (WebRTC) | 🚧 In Development |
| [media-service](https://github.com/tayank-inc/media-service) | File storage & CDN | 📋 Planned |
| [presence-service](https://github.com/tayank-inc/presence-service) | User presence & activity | 📋 Planned |
| [notification-service](https://github.com/tayank-inc/notification-service) | Push notifications | 📋 Planned |
| [search-service](https://github.com/tayank-inc/search-service) | Search (Elasticsearch) | 📋 Planned |
| [moderation-service](https://github.com/tayank-inc/moderation-service) | Content moderation (AI) | 📋 Planned |
| [analytics-service](https://github.com/tayank-inc/analytics-service) | Analytics & metrics | 📋 Planned |
| [billing-service](https://github.com/tayank-inc/billing-service) | Payments & subscriptions | 📋 Planned |
| [api-gateway](https://github.com/tayank-inc/api-gateway) | API Gateway & routing | 🚧 In Development |

### 🎨 Frontend Applications

| App | Description | Platform |
|-----|-------------|----------|
| [web](https://github.com/tayank-inc/web) | Web application | Next.js 15 |
| [mobile](https://github.com/tayank-inc/mobile) | Mobile app | Flutter |
| [landing](https://github.com/tayank-inc/landing) | Marketing website | Next.js |

### 📚 Shared Libraries

| Package | Description | Language |
|---------|-------------|----------|
| [proto](https://github.com/tayank-inc/proto) | Protocol Buffers (gRPC) | Proto |
| [shared-go](https://github.com/tayank-inc/shared-go) | Go utilities | Go |
| [shared-ts](https://github.com/tayank-inc/shared-ts) | TypeScript utilities | TypeScript |
| [ui-components](https://github.com/tayank-inc/ui-components) | React component library | React |
| [sdk](https://github.com/tayank-inc/sdk) | Client SDKs (JS, Python, Go) | Multi-language |

### 🏠 Main Repository

| Repository | Description |
|------------|-------------|
| [tayank](https://github.com/tayank-inc/tayank) | Main orchestration repo (infrastructure, docs, docker-compose) |

---

## 🚀 Quick Start

### For Developers

```bash
# Clone main repo
git clone https://github.com/tayank-inc/tayank.git
cd tayank

# Start local development environment
docker-compose up -d

# Access:
# - Web: http://localhost:3000
# - API: http://localhost:8080
# - Docs: http://localhost:8000
```

### For Users

- 🌐 **Web**: [app.tayank.com](https://app.tayank.com)
- 📱 **iOS**: Coming soon
- 🤖 **Android**: Coming soon
- 💻 **Desktop**: Coming soon

---

## 📚 Resources

- 📖 [Documentation](https://docs.tayank.com) - Complete guides and API reference
- 🎓 [Developer Guides](https://docs.tayank.com/guides) - Build bots and integrations
- 🔌 [API Reference](https://api.tayank.com/docs) - REST & WebSocket APIs
- 🤖 [Bot Development](https://docs.tayank.com/bots) - Create powerful bots

---

## 🤝 Contributing

We welcome contributions from the community! 

**Before contributing:**
1. Read our [Contributing Guide](https://github.com/tayank-inc/.github/blob/main/CONTRIBUTING.md)
2. Check our [Code of Conduct](https://github.com/tayank-inc/.github/blob/main/CODE_OF_CONDUCT.md)
3. Look for issues labeled [`good first issue`](https://github.com/search?q=org%3Atayank-inc+label%3A%22good+first+issue%22+state%3Aopen&type=Issues)

**How to contribute:**
- 🐛 [Report bugs](https://github.com/tayank-inc/tayank/issues/new?template=bug_report.yml)
- ✨ [Request features](https://github.com/tayank-inc/tayank/issues/new?template=feature_request.yml)
- 📝 Improve documentation
- 🔧 Submit pull requests

---

## 🛡️ Security

Security is our top priority. If you discover a security vulnerability:

**🚨 DO NOT open a public issue!**

Instead, please:
- Email: [security@tayank.com](mailto:security@tayank.com)
- Read our [Security Policy](https://github.com/tayank-inc/.github/blob/main/SECURITY.md)

---

## 📊 Project Status

| Metric | Status |
|--------|--------|
| Version | v0.1.0-alpha (MVP in development) |
| Services | 11 planned, 3 in development |
| Test Coverage | Target: 80%+ |
| Documentation | In progress |
| Public Launch | Q2 2025 (estimated) |

---

## 🌟 Features Roadmap

### V1.0 - MVP (Current)
- ✅ Text channels & DMs
- ✅ Voice channels
- ✅ Basic roles & permissions
- ✅ File sharing
- 🚧 Real-time messaging
- 🚧 User authentication

### V2.0 - Enhanced
- 📋 Video streaming
- 📋 Screen sharing
- 📋 Threads
- 📋 Forum channels
- 📋 Bots & webhooks
- 📋 Mobile apps

### V3.0 - Enterprise
- 📋 Workspaces (business tier)
- 📋 Advanced analytics
- 📋 SSO integration
- 📋 Compliance features

---

## 📞 Contact

- 🌐 Website: [tayank.com](https://tayank.com)
- 📧 Email: [hello@tayank.com](mailto:hello@tayank.com)
- 🐦 Twitter: [@tayankapp](https://twitter.com/tayankapp)
- 📺 YouTube: [Tayank Official](https://youtube.com/@tayank)

---

## 📄 License

Most of our projects are licensed under the [MIT License](LICENSE).

Individual repositories may have different licenses - please check each repo's LICENSE file.

---

## ❤️ Sponsors

We're grateful to our sponsors who help make Tayank possible:

<!-- Sponsors section - will be populated later -->
*Become a sponsor and help us build the future of communication!*

---

<div align="center">

**Built with ❤️ by the Tayank team**

[⭐ Star us on GitHub](https://github.com/tayank-inc) • [📖 Read the docs](https://docs.tayank.com)

</div>
```

---

## 2️⃣ ISSUE_TEMPLATE/bug_report.yml

```yaml
name: 🐛 Bug Report
description: Report a bug or unexpected behavior
title: "[Bug]: "
labels: ["type: bug", "status: needs-triage"]
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        Thanks for taking the time to report a bug! Please fill out the form below.
        
        **Before submitting:**
        - Search existing issues to avoid duplicates
        - Make sure you're using the latest version

  - type: textarea
    id: description
    attributes:
      label: Description
      description: A clear and concise description of what the bug is.
      placeholder: "When I try to send a message in #general, it doesn't appear..."
    validations:
      required: true

  - type: textarea
    id: steps
    attributes:
      label: Steps to Reproduce
      description: How can we reproduce this bug?
      placeholder: |
        1. Go to '...'
        2. Click on '...'
        3. Scroll down to '...'
        4. See error
    validations:
      required: true

  - type: textarea
    id: expected
    attributes:
      label: Expected Behavior
      description: What did you expect to happen?
      placeholder: "The message should appear in the channel..."
    validations:
      required: true

  - type: textarea
    id: actual
    attributes:
      label: Actual Behavior
      description: What actually happened?
      placeholder: "The message doesn't appear and I see an error..."
    validations:
      required: true

  - type: dropdown
    id: component
    attributes:
      label: Component
      description: Which part of Tayank is affected?
      options:
        - Web App
        - Mobile App (iOS)
        - Mobile App (Android)
        - Desktop App
        - API
        - Voice/Video
        - Authentication
        - Messaging
        - File Upload
        - Search
        - Notifications
        - Other
    validations:
      required: true

  - type: dropdown
    id: severity
    attributes:
      label: Severity
      description: How severe is this bug?
      options:
        - Critical (App crashes, data loss, security issue)
        - High (Major feature broken)
        - Medium (Feature partially broken)
        - Low (Minor inconvenience)
    validations:
      required: true

  - type: input
    id: version
    attributes:
      label: Version
      description: What version of Tayank are you using?
      placeholder: "v1.2.3 or commit hash"
    validations:
      required: false

  - type: dropdown
    id: platform
    attributes:
      label: Platform
      description: What platform are you using?
      multiple: true
      options:
        - Web (Chrome)
        - Web (Firefox)
        - Web (Safari)
        - Web (Edge)
        - iOS
        - Android
        - Windows
        - macOS
        - Linux

  - type: textarea
    id: environment
    attributes:
      label: Environment Details
      description: Any relevant details about your environment
      placeholder: |
        - OS: Windows 11
        - Browser: Chrome 120.0
        - Screen Resolution: 1920x1080
        - Network: WiFi
      render: markdown

  - type: textarea
    id: logs
    attributes:
      label: Relevant Logs/Screenshots
      description: |
        Please paste any relevant logs or add screenshots.
        **Tip:** You can attach images by dragging and dropping.
      placeholder: |
        Paste logs here or attach screenshots
      render: shell

  - type: textarea
    id: additional
    attributes:
      label: Additional Context
      description: Any other information that might be relevant
      placeholder: "This only happens when..."

  - type: checkboxes
    id: terms
    attributes:
      label: Checklist
      options:
        - label: I have searched existing issues to avoid duplicates
          required: true
        - label: I have provided all the information requested above
          required: true
        - label: This issue is reproducible
          required: false
```

---

## 3️⃣ ISSUE_TEMPLATE/feature_request.yml

```yaml
name: ✨ Feature Request
description: Suggest a new feature or improvement
title: "[Feature]: "
labels: ["type: feature", "status: needs-triage"]
assignees: []

body:
  - type: markdown
    attributes:
      value: |
        Thanks for suggesting a feature! We appreciate your input.
        
        **Before submitting:**
        - Check if this feature has already been requested
        - Make sure it aligns with Tayank's goals

  - type: textarea
    id: problem
    attributes:
      label: Problem Statement
      description: What problem does this feature solve?
      placeholder: "I'm always frustrated when..."
    validations:
      required: true

  - type: textarea
    id: solution
    attributes:
      label: Proposed Solution
      description: Describe your proposed solution in detail
      placeholder: "I would like to see..."
    validations:
      required: true

  - type: textarea
    id: alternatives
    attributes:
      label: Alternatives Considered
      description: What alternative solutions have you considered?
      placeholder: "I've also thought about..."
    validations:
      required: false

  - type: dropdown
    id: component
    attributes:
      label: Component
      description: Which part of Tayank would this affect?
      options:
        - Web App
        - Mobile App
        - Desktop App
        - API
        - Voice/Video
        - Messaging
        - Servers/Channels
        - User Profile
        - Notifications
        - Search
        - Moderation
        - Bots/Integrations
        - Other
    validations:
      required: true

  - type: dropdown
    id: user-type
    attributes:
      label: User Type
      description: Who would benefit from this feature?
      multiple: true
      options:
        - Regular Users
        - Server Owners
        - Moderators
        - Developers/Bot Creators
        - Business/Workspace Users
        - All Users

  - type: dropdown
    id: priority
    attributes:
      label: Priority (Your Opinion)
      description: How important is this feature to you?
      options:
        - Must Have (Can't use Tayank without it)
        - Should Have (Very important)
        - Nice to Have (Would be useful)
        - Low Priority (Small improvement)
    validations:
      required: true

  - type: textarea
    id: use-case
    attributes:
      label: Use Case / User Story
      description: Describe how you (or others) would use this feature
      placeholder: |
        As a [user type],
        I want to [do something],
        So that [achieve goal]
    validations:
      required: false

  - type: textarea
    id: mockups
    attributes:
      label: Mockups/Examples
      description: |
        Do you have any mockups, wireframes, or examples from other apps?
        **Tip:** You can attach images by dragging and dropping.
      placeholder: "Attach images or describe visual design"

  - type: textarea
    id: technical
    attributes:
      label: Technical Considerations
      description: Any technical details, constraints, or implementation ideas?
      placeholder: "This might require..."

  - type: textarea
    id: additional
    attributes:
      label: Additional Context
      description: Any other information that might be relevant

  - type: checkboxes
    id: terms
    attributes:
      label: Checklist
      options:
        - label: I have searched existing issues to avoid duplicates
          required: true
        - label: This feature aligns with Tayank's goals (communication platform)
          required: true
        - label: I have provided sufficient detail for the feature to be understood
          required: true
```

---

## 4️⃣ ISSUE_TEMPLATE/config.yml

```yaml
blank_issues_enabled: false
contact_links:
  - name: 📚 Documentation
    url: https://docs.tayank.com
    about: Check our documentation for guides and API reference
  
  - name: 🔐 Security Vulnerability
    url: mailto:security@tayank.com
    about: Report security vulnerabilities privately via email
  
  - name: 💡 Feature Discussion
    url: https://github.com/orgs/tayank-inc/discussions
    about: Discuss new ideas and features with the community
  
  - name: 📧 General Support
    url: mailto:support@tayank.com
    about: Contact support for account or usage questions
```

---

## 5️⃣ PULL_REQUEST_TEMPLATE.md

```markdown
## Description

<!-- Provide a brief description of your changes -->

Fixes #(issue number)

## Type of Change

<!-- Mark the relevant option with an 'x' -->

- [ ] 🐛 Bug fix (non-breaking change which fixes an issue)
- [ ] ✨ New feature (non-breaking change which adds functionality)
- [ ] 💥 Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] 📝 Documentation update
- [ ] 🎨 Style/UI update (non-functional change)
- [ ] ♻️ Code refactoring (no functional changes)
- [ ] ⚡ Performance improvement
- [ ] ✅ Test update
- [ ] 🔧 Configuration change
- [ ] 🏗️ Infrastructure change

## Changes Made

<!-- List the specific changes you made -->

- 
- 
- 

## Testing

<!-- Describe the tests you ran and how to reproduce them -->

- [ ] Unit tests pass (`go test ./...` or `npm test`)
- [ ] Integration tests pass
- [ ] Manual testing completed
- [ ] All existing tests pass

**Test Configuration:**
- OS:
- Go version / Node version:
- Database version (if applicable):

## Screenshots (if applicable)

<!-- Add screenshots to help explain your changes -->

## Checklist

<!-- Mark completed items with an 'x' -->

- [ ] My code follows the project's style guidelines
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings or errors
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes
- [ ] Any dependent changes have been merged and published
- [ ] I have checked my code and corrected any misspellings

## Breaking Changes

<!-- If this is a breaking change, describe the impact and migration path -->

- [ ] This PR introduces breaking changes
- [ ] Migration guide has been provided

**Migration Notes:**
<!-- If applicable, describe how users should update their code -->

## Dependencies

<!-- List any dependencies that are required for this change -->

- [ ] No new dependencies
- [ ] New dependencies added (list below)

**New Dependencies:**
- 

## Deployment Notes

<!-- Any special deployment considerations? -->

- [ ] Requires database migration
- [ ] Requires environment variable changes
- [ ] Requires infrastructure updates
- [ ] Can be deployed independently

## Related Issues/PRs

<!-- Link related issues or PRs -->

- Related to #
- Depends on #
- Blocks #

## Additional Notes

<!-- Any additional information that reviewers should know -->

---

## For Reviewers

**Focus Areas:**
<!-- Tell reviewers where to focus their attention -->

- 
- 

**Questions for Reviewers:**
<!-- Any specific questions or concerns? -->

- 
- 

---

**By submitting this PR, I confirm that:**
- [ ] I have read and followed the [Contributing Guidelines](../CONTRIBUTING.md)
- [ ] I have read and agree to the [Code of Conduct](../CODE_OF_CONDUCT.md)
- [ ] My contribution is original and I have the right to submit it under the project's license
```

---

## 6️⃣ CONTRIBUTING.md

```markdown
# Contributing to Tayank

First off, thank you for considering contributing to Tayank! 🎉

It's people like you that make Tayank such a great platform.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Testing Guidelines](#testing-guidelines)
- [Documentation](#documentation)

---

## 📜 Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

---

## 🤝 How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates.

**How to submit a good bug report:**
- Use our [bug report template](.github/ISSUE_TEMPLATE/bug_report.yml)
- Provide a clear title and description
- Include steps to reproduce
- Add screenshots/logs if applicable
- Specify your environment (OS, browser, version)

### Suggesting Features

We love feature suggestions!

**How to submit a good feature request:**
- Use our [feature request template](.github/ISSUE_TEMPLATE/feature_request.yml)
- Explain the problem you're trying to solve
- Describe your proposed solution
- Consider alternatives
- Think about impact on existing users

### Contributing Code

**Good First Issues:**
Look for issues labeled [`good first issue`](https://github.com/search?q=org%3Atayank-inc+label%3A%22good+first+issue%22+state%3Aopen&type=Issues) - these are great for newcomers!

**Steps to contribute:**
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Write/update tests
5. Run tests (`make test`)
6. Commit your changes (follow [commit guidelines](#commit-guidelines))
7. Push to your fork (`git push origin feature/amazing-feature`)
8. Open a Pull Request

---

## 🛠️ Development Setup

### Prerequisites

- **Go**: 1.21+
- **Node.js**: 18+
- **Docker**: 20+
- **Docker Compose**: 2.0+
- **Git**: 2.30+

### Initial Setup

```bash
# Clone main repository
git clone https://github.com/tayank-inc/tayank.git
cd tayank

# Start infrastructure (PostgreSQL, Redis, Kafka, etc.)
docker-compose up -d

# Run database migrations
make migrate

# Start all services (development mode)
make dev
```

### Repository Structure

```
tayank/
├── services/          # Backend microservices (Go)
├── apps/             # Frontend applications
├── packages/         # Shared libraries
├── infrastructure/   # Terraform, K8s configs
├── docs/            # Documentation
└── scripts/         # Utility scripts
```

### Service-Specific Setup

**Backend (Go):**
```bash
cd services/auth-service
go mod download
go build ./cmd/server
go test ./...
```

**Frontend (Next.js):**
```bash
cd apps/web
npm install
npm run dev
npm test
```

**Mobile (Flutter):**
```bash
cd apps/mobile
flutter pub get
flutter run
flutter test
```

---

## 🔄 Pull Request Process

### Before Submitting

1. **Update documentation** - README, API docs, etc.
2. **Write tests** - Maintain 80%+ code coverage
3. **Run linters** - `make lint`
4. **Run all tests** - `make test`
5. **Update CHANGELOG** - Add entry under "Unreleased"
6. **Self-review** - Review your own code first

### PR Requirements

- [ ] Clear title (follow convention below)
- [ ] Description explains what and why
- [ ] All tests pass
- [ ] Code coverage maintained/improved
- [ ] Documentation updated
- [ ] No merge conflicts
- [ ] Approved by at least 1 reviewer

### PR Title Convention

```
<type>(<scope>): <subject>

Examples:
feat(auth): add OAuth2 support
fix(messaging): resolve memory leak in WebSocket
docs(api): update authentication guide
refactor(voice): improve codec efficiency
test(billing): add Stripe webhook tests
```

**Types:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation only
- `style` - Formatting, missing semi-colons, etc.
- `refactor` - Code restructuring
- `perf` - Performance improvement
- `test` - Adding/updating tests
- `chore` - Maintenance tasks

### Review Process

1. **Automated checks** - CI/CD runs automatically
2. **Code review** - Maintainers review within 48 hours
3. **Changes requested** - Address feedback
4. **Approval** - At least 1 approval required
5. **Merge** - Maintainers merge (usually squash & merge)

---

## 💻 Coding Standards

### Go

**Style Guide:** Follow [Effective Go](https://golang.org/doc/effective_go.html)

```go
// ✅ Good
func (s *AuthService) CreateUser(ctx context.Context, req *CreateUserRequest) (*User, error) {
    if err := s.validator.Validate(req); err != nil {
        return nil, fmt.Errorf("validation failed: %w", err)
    }
    
    // ... implementation
}

// ❌ Bad
func createUser(r *CreateUserRequest) *User {
    // Missing context, error handling, validation
}
```

**Rules:**
- Use `gofmt` for formatting
- Run `golangci-lint` before committing
- Write descriptive variable names (no single letters except loops)
- Add comments for exported functions
- Handle ALL errors
- Use context for cancellation/timeouts
- Keep functions small (<50 lines)

### TypeScript/JavaScript

**Style Guide:** Follow [Airbnb JavaScript Style Guide](https://github.com/airbnb/javascript)

```typescript
// ✅ Good
interface User {
  id: string;
  username: string;
  email: string;
}

async function fetchUser(userId: string): Promise<User> {
  const response = await api.get(`/users/${userId}`);
  return response.data;
}

// ❌ Bad
function getUser(id) {
  // Missing types, async/await
  return api.get('/users/' + id).then(r => r.data);
}
```

**Rules:**
- Use TypeScript (no `any` type)
- Use `async/await` over `.then()`
- Use `const` over `let`, never `var`
- Use arrow functions for callbacks
- Run ESLint and Prettier
- Write JSDoc comments for complex functions

### Flutter/Dart

**Style Guide:** Follow [Effective Dart](https://dart.dev/guides/language/effective-dart)

```dart
// ✅ Good
class UserRepository {
  Future<User> fetchUser(String userId) async {
    final response = await _api.get('/users/$userId');
    return User.fromJson(response.data);
  }
}

// ❌ Bad
fetchUser(id) {
  return _api.get('/users/' + id).then((r) => User.fromJson(r.data));
}
```

---

## 📝 Commit Guidelines

### Conventional Commits

We follow [Conventional Commits](https://www.conventionalcommits.org/).

**Format:**
```
<type>(<scope>): <subject>

<body>

<footer>
```

**Example:**
```
feat(auth): add OAuth2 login flow

Implement OAuth2 authorization code flow with support for
Google, GitHub, and Microsoft providers.

- Add OAuth2 client configuration
- Implement token exchange
- Add user profile fetching
- Update login UI

Closes #123
```

**Types:**
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Formatting
- `refactor` - Code restructuring
- `perf` - Performance
- `test` - Testing
- `build` - Build system
- `ci` - CI/CD
- `chore` - Maintenance

**Rules:**
- Use present tense ("add feature" not "added feature")
- Use imperative mood ("move cursor" not "moves cursor")
- Don't capitalize first letter
- No period at the end
- Reference issues/PRs in footer

---

## 🧪 Testing Guidelines

### Test Coverage

- **Minimum**: 80% code coverage
- **Target**: 90%+ for critical services (auth, billing)

### Test Pyramid

```
       /\
      /  \     E2E (10%)
     /____\    
    /      \   Integration (30%)
   /________\  
  /          \ Unit (60%)
 /____________\
```

### Writing Tests

**Go:**
```go
func TestCreateUser(t *testing.T) {
    // Arrange
    service := NewAuthService(mockRepo)
    req := &CreateUserRequest{
        Username: "testuser",
        Email:    "test@example.com",
    }
    
    // Act
    user, err := service.CreateUser(context.Background(), req)
    
    // Assert
    assert.NoError(t, err)
    assert.NotNil(t, user)
    assert.Equal(t, "testuser", user.Username)
}
```

**TypeScript:**
```typescript
describe('fetchUser', () => {
  it('should fetch user successfully', async () => {
    // Arrange
    const userId = '123';
    mockApi.get.mockResolvedValue({ data: mockUser });
    
    // Act
    const user = await fetchUser(userId);
    
    // Assert
    expect(user).toEqual(mockUser);
    expect(mockApi.get).toHaveBeenCalledWith('/users/123');
  });
});
```

### Running Tests

```bash
# Go (unit + integration)
make test

# JavaScript/TypeScript
npm test

# Flutter
flutter test

# E2E tests
npm run test:e2e

# With coverage
make test-coverage
```

---

## 📚 Documentation

### What to Document

- **All public APIs** - Every exported function/class
- **Complex logic** - Explain the "why", not just the "what"
- **Architecture decisions** - Add ADRs in `/docs/architecture/`
- **Setup instructions** - Keep README.md updated
- **Breaking changes** - Always document in CHANGELOG

### Documentation Standards

**Go:**
```go
// CreateUser creates a new user account with the provided credentials.
// It validates the input, hashes the password, and stores the user in the database.
//
// Parameters:
//   - ctx: Context for cancellation and timeouts
//   - req: User creation request with username, email, and password
//
// Returns:
//   - *User: Created user object
//   - error: Validation or database errors
//
// Example:
//   user, err := service.CreateUser(ctx, &CreateUserRequest{
//       Username: "john",
//       Email: "john@example.com",
//       Password: "secure123",
//   })
func (s *AuthService) CreateUser(ctx context.Context, req *CreateUserRequest) (*User, error) {
    // ...
}
```

**TypeScript:**
```typescript
/**
 * Fetches a user by ID from the API
 * 
 * @param userId - The unique identifier of the user
 * @returns Promise resolving to the user object
 * @throws {ApiError} When the user is not found or API request fails
 * 
 * @example
 * ```ts
 * const user = await fetchUser('123');
 * console.log(user.username);
 * ```
 */
async function fetchUser(userId: string): Promise<User> {
  // ...
}
```

---

## 🏷️ Issue Labels

We use labels to organize and prioritize issues:

**Type:**
- `type: bug` - Something isn't working
- `type: feature` - New feature request
- `type: docs` - Documentation improvement
- `type: refactor` - Code restructuring
- `type: performance` - Performance improvement

**Priority:**
- `priority: critical` - Urgent, breaks core functionality
- `priority: high` - Important, should be done soon
- `priority: medium` - Normal priority
- `priority: low` - Nice to have

**Status:**
- `status: needs-triage` - Needs initial review
- `status: needs-info` - Waiting for more information
- `status: blocked` - Blocked by another issue
- `status: in-progress` - Currently being worked on
- `status: needs-review` - Ready for review

**Special:**
- `good first issue` - Good for newcomers
- `help wanted` - Community help needed
- `breaking change` - Introduces breaking changes
- `security` - Security-related issue

---

## 🎯 Development Workflow

### Branch Strategy

```
main (production)
  ↑
develop (staging)
  ↑
feature/xxx (feature branches)
```

**Branch Naming:**
- `feature/add-oauth` - New features
- `fix/memory-leak` - Bug fixes
- `docs/api-guide` - Documentation
- `refactor/auth-service` - Refactoring
- `hotfix/security-patch` - Urgent fixes

### Release Process

1. Create release branch from `develop`
2. Bump version in all packages
3. Update CHANGELOG.md
4. Create PR to `main`
5. After merge, tag release: `v1.2.3`
6. Deploy to production
7. Merge back to `develop`

---

## ❓ Questions?

- 📧 Email: [contribute@tayank.com](mailto:contribute@tayank.com)
- 📚 [Documentation](https://docs.tayank.com)

---

## 🙏 Thank You!

Your contributions make Tayank better for everyone. We appreciate your time and effort! ❤️

**Happy coding! 🚀**