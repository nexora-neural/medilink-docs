# MediLink Contribution Guide

This guide applies to `medilink-backend`, `medilink-frontend`, and `medilink-docs`. Follow the approved MediLink scope, Team Guide, Developer Guide, API Contract, and database baseline. Raise conflicts between a repository and the approved baseline before implementing the affected work.

## Branches

Create a short-lived branch for one Jira task. Use these prefixes and include the Jira key:

- `feat/ML-123-short-description` for a feature
- `fix/ML-123-short-description` for a defect
- `docs/ML-123-short-description` for documentation
- `chore/ML-123-short-description` for maintenance

Use lowercase kebab-case descriptions. Keep `main` as the shared integration branch. Do not commit unfinished work directly to `main`; submit changes through a pull request.

## Commit messages

Use `type(scope): short imperative summary`, for example `feat(auth): add session validation`. Use the Jira key in the pull request title or description. Keep commits focused and avoid generated output, local configuration, credentials, and patient data.

## Code and documentation

Follow the conventions already configured in each repository. For the frontend, respect `.editorconfig`, `.prettierrc`, Angular conventions, and the committed lockfile. For the backend, follow the existing Python style and project structure. Do not introduce a formatter, linter, dependency, or runtime version without team agreement. Keep API contract, OpenAPI, database design, and ORM changes aligned; document setup or behavior changes in the relevant README or docs.

## Pull requests and review

Open one pull request per Jira task and link the ML issue. Describe the purpose, key changes, verification performed, risks or migration/API impact, and screenshots for UI changes. Request review from a teammate; the author should address review comments and obtain at least one approval before merge. Resolve conversations and confirm the change matches the agreed scope.

Before requesting review, check that:

- [ ] The change is limited to the linked task and follows the approved project baseline.
- [ ] Relevant checks were run and results are recorded.
- [ ] API, database, setup, or user documentation is updated when affected.
- [ ] No secrets, credentials, or real patient data are included.
- [ ] Frontend dependencies and `package.json` / `package-lock.json` remain in sync.
- [ ] Any known limitation or follow-up is stated clearly.

## Security and data handling

Use synthetic data for development and examples. Never commit secrets, private keys, real patient records, or local environment files. Keep access to the minimum needed and report suspected exposure to the project owner promptly.
