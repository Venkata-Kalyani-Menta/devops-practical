# Matrix Demo

A simple Node.js project demonstrating GitHub Actions Matrix Testing across multiple operating systems (Ubuntu, Windows, and macOS).

## Project Structure

```text
matrix-demo/
├── .github/
│   └── workflows/
│       └── matrix-test.yml
├── app.js
├── test.js
└── package.json
```

## Prerequisites

- Node.js 20 or later
- npm
- Git (optional, for pushing to GitHub)

Verify installation:

```bash
node -v
npm -v
```

## Setup

### Clone the Repository

```bash
git clone <repository-url>
cd matrix-demo
```

Or create the files manually as described in this project.

### Install Dependencies

```bash
npm install
```

> Note: This project currently has no external dependencies, but this command is included as a standard practice.

## Run the Test Locally

Execute the test directly:

```bash
node test.js
```

Expected output:

```text
All tests passed!
```

Or run the npm test script:

```bash
npm test
```

## Application Code

`app.js`

```javascript
function add(a, b) {
    return a + b;
}

module.exports = { add };
```

## Test Code

`test.js`

```javascript
const assert = require("assert");
const { add } = require("./app");

assert.strictEqual(add(2, 3), 5);

console.log("All tests passed!");
```

## GitHub Actions Workflow

The workflow runs automatically on:

- Push events
- Pull Request events

Supported platforms:

- Ubuntu
- Windows
- macOS

Workflow file:

```text
.github/workflows/matrix-test.yml
```

### Matrix Strategy

```yaml
strategy:
  matrix:
    os:
      - ubuntu-latest
      - windows-latest
      - macos-latest
```

GitHub Actions creates three parallel jobs and executes the same test on each operating system.

## Triggering the Workflow

Commit and push changes:

```bash
git add .
git commit -m "Add matrix testing example"
git push origin main
```

Navigate to:

```text
GitHub Repository → Actions
```

You should see the workflow running for all three operating systems.

## Expected Workflow Steps

1. Checkout repository
2. Setup Node.js
3. Install dependencies
4. Run tests

## Example Success Output

```text
✓ Ubuntu - Passed
✓ Windows - Passed
✓ macOS - Passed
```

## Learning Objectives

This project demonstrates:

- JavaScript functions
- Node.js modules (`require`, `module.exports`)
- Basic unit testing with `assert`
- npm scripts
- GitHub Actions workflows
- Matrix strategy
- Continuous Integration (CI)

## Useful Commands

```bash
# Run tests
npm test

# Run JavaScript file
node test.js

# Check Node version
node -v

# Check npm version
npm -v

# Check git status
git status

# Commit changes
git commit -m "message"

# Push code
git push
```
