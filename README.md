
# Vue-App CI/CD Workflow

This project demonstrates a CI/CD pipeline using GitHub Actions for a Vue.js frontend and an Express backend. The pipeline is configured to run frontend and backend tests, perform dependency audits, and deploy the application when changes are pushed to the `main` branch.  
The web application comes from the GitHub repository [dymafr/cicd-projet1](https://github.com/dymafr/cicd-projet1), which is used solely to test GitHub Actions and the CI/CD pipeline.

## Workflow Overview

The GitHub Actions workflow is split into three main jobs:

1. **Test Frontend**: Runs frontend tests and checks.
2. **Test Backend**: Runs backend tests and checks.
3. **Deployment**: Deploys the application after successful tests.

The workflow is triggered by `push` events to the `main` branch, with specific conditions based on the commit message.

## Workflow Configuration

The workflow configuration is located in the `.github/workflows/vue-app.yml` file.

## How to Trigger the Workflows

The workflows are triggered by specific commit messages. Here's how to trigger each workflow manually:

### 1. Trigger Frontend Tests

To trigger the frontend test job, include `test-frontend` in your commit message. For example:

```bash
git commit -m "test-frontend: Run tests and lint"
git push origin main
```

This will trigger the `test-frontend` job, which will run frontend build, linting, and end-to-end tests.

#### Tools Used in `test-frontend`:

- **ESLint**: A static code analysis tool used to identify and fix problems in JavaScript code, ensuring consistent code style and catching potential errors. It's run in the `Linter` step.
- **Cypress**: A JavaScript end-to-end testing framework used to test the full functionality of the application in a real browser.

### 2. Trigger Backend Tests

To trigger the backend test job, include `test-backend` in your commit message. For example:

```bash
git commit -m "test-backend: Run backend unit tests"
git push origin main
```

This will trigger the `test-backend` job, which will run the backend unit tests and dependency audits.

#### Tools Used in `test-backend`:

- **ESLint**: As in the frontend job, ESLint is also used in the backend to ensure code quality and style consistency.
- **Jest**: A testing framework for JavaScript used to run unit tests on the backend code.

### 3. Trigger Deployment

To trigger the deployment job, include `deploy` in your commit message. For example:

```bash
git commit -m "deploy: Deploy the app to production"
git push origin main
```

This will trigger the `deployment` job, which will deploy the application and check the code using ESLint.

## Prerequisites

- Node.js and npm are required for both frontend and backend projects.
- Cypress is required for end-to-end testing in the frontend job.
- The Express server should be set up to run for end-to-end testing.
