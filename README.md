# GitHub Actions Automation Project

This repository contains a set of GitHub Actions workflows designed to automate development tasks, enforce code quality, and provide actionable annotations for code changes.

---

## Workflows

### 1. Deprecated Function Detection

- **File:** `.github/workflows/expression.yml`  
- **Trigger:** `workflow_dispatch`  
- **Description:** Scans source files for deprecated code patterns and generates annotations (warnings, errors, notices) in GitHub.  
- **Example Annotation Syntax:**  

```bash
::warning file=src/test.sh,line=1,col=1::Deprecated function found

2. Matrix Jobs Execution

File: .github/workflows/Metrics-strategy.yml

Trigger: Push to main

Description: Runs jobs in parallel using matrices and dependencies for efficient workflow execution.

3. Docker & VM Steps

File: .github/workflows/actions.yml

Description: Demonstrates running steps in multiple environments:

Ubuntu VM

Alpine Docker container

Back to VM for additional commands
How to Run Workflows

Manually trigger a workflow:

Go to your repository → Actions → select the workflow → Run workflow → choose the branch → Run workflow.

Trigger via push:

git add .
git commit -m "Update workflows"
git push origin main

View Annotations:

Open the workflow run → click on logs.

Warnings, errors, and notices are highlighted in the logs.

On pull requests, annotations appear inline in the diff for easy review.

Deprecated Function Detection Example

You can mark lines in scripts as deprecated. Example in src/test.sh:

deprecated=true
if [[ $deprecated == true ]]; then
  echo "::warning file=src/test.sh,line=1,col=1::Deprecated function found"
fi

Using GitHub Actions Secrets

Do not commit sensitive tokens or credentials.

Store secrets in GitHub Actions:
env:
  MY_TOKEN: ${{ secrets.MY_GITHUB_TOKEN }}

  Access the secret in scripts:

echo "Token is $MY_TOKEN"

Repository Structure

.github/
  workflows/
    expression.yml
    actions.yml
    Metrics-strategy.yml

    Workflows: Automation for code checks, matrix jobs, and environment-specific commands.

src/: Contains scripts executed by the workflows.

src/
  test.sh
  


