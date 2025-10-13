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