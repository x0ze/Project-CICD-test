# Vue-App CI/CD Workflow

This project demonstrates a CI/CD pipeline using GitHub Actions for a Vue.js frontend and an Express backend. The pipeline is configured to run frontend and backend tests, perform dependency audits, and deploy the application when changes are pushed to the `main` branch.

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

### 2. Trigger Backend Tests

To trigger the backend test job, include `test-backend` in your commit message. For example:

```bash
git commit -m "test-backend: Run backend unit tests"
git push origin main
```
This will trigger the `test-backend` job, which will run the backend unit tests and dependency audits.

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

