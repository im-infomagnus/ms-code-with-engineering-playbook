# How to Import Playbook Tasks into GitHub Issues

This guide walks you through importing engineering playbook tasks into your project's GitHub repository as Issues. By the end, you'll have a full set of playbook tasks available in your repo's **Projects** board and **Issues** tab.

## Prerequisites

- You have access to the [InfoMagnus engineering playbook repo](https://github.com/im-infomagnus/ms-code-with-engineering-playbook)
- You have admin (or sufficient) permissions on your project's GitHub repository
- You have permissions to create a Personal Access Token (PAT) for your GitHub account

---

## Steps

### Step 1 — Copy the Workflow File from the Playbook Repo

1. Navigate to the playbook repo: [https://github.com/im-infomagnus/ms-code-with-engineering-playbook](https://github.com/im-infomagnus/ms-code-with-engineering-playbook)
2. Find the file: `.github/workflows/pull-project-tasks.yml`
3. Click on the file, then click the **Copy raw file** button (or click **Raw** and copy all of the YAML contents). You will paste this into your own repo in the next steps.

### Step 2 — Create the Workflows Folder in Your Project Repo

1. Within your project repo, make sure a `.github/workflows` folder exists in the root of the project.
   - You can create this via the GitHub UI by clicking **Add file > Create new file** and typing `.github/workflows/` as the beginning of the file path.

> **Important:** The `.github` folder **must** begin with a period (`.`) and be located directly in the project's root. The child folder `workflows` **must** be located directly inside the `.github` folder and named exactly `workflows`.

### Step 3 — Create the Workflow File

1. Within the `workflows` folder, create a file called `pull-project-tasks.yml`.
2. Paste the YAML content you copied in **Step 1** into this file and save it.

### Step 4 — Push the Workflow File to GitHub

1. If not already pushed to GitHub, make sure the new `.github/workflows/pull-project-tasks.yml` file is committed and pushed to your project's repo.

### Step 5 — Create a GitHub Project

1. Navigate to the main page of your project's repo and click the **Projects** tab in the header navigation bar.
2. On the Projects page, click the green **Link a project** button, then select **New project**.
3. In the dialog that appears, select either **Table** or **Board** in the left sidebar (Table is recommended).
4. Give your project a name and click **Create project**.

> **Note:** This is the Project you will import Issues/tasks into. You will need to reference this project's name when running the workflow later.

### Step 6 — Create a Personal Access Token (PAT)

1. Click your **profile avatar** in the upper-right corner of GitHub and select **Settings** from the dropdown menu.
2. On the Settings page, scroll to the bottom of the left sidebar and click **Developer settings**.
3. In the left nav, expand **Personal access tokens** and select **Tokens (classic)**.
4. Click **Generate new token** > **Generate new token (classic)**.
5. Give your token a descriptive name (e.g., `playbook-import-token`) and configure the following scopes:
   - **repo** — Full control of private repositories ✅
   - **admin:org > read:org** — Read org membership ✅
   - **project** — Full control of projects ✅
6. Click **Generate token** at the bottom of the page.
7. **Copy the token value immediately** — you will not be able to see it again after leaving this page.

> **Important:** If your organization uses SSO, you will also need to authorize the token for SSO. On the **Personal access tokens** page, find your token and click **Configure SSO**, then click **Authorize** next to your organization.

### Step 7 — Add the PAT as a Repository Secret

1. Navigate back to the main page of your project's repo and click **Settings** in the header navigation bar (far right).
2. In the left sidebar, click **Secrets and variables** and then select **Actions**.
3. Click the green **New repository secret** button.
4. Enter a name for the secret (e.g., `PLAYBOOK_PAT`) and paste the token value you copied in **Step 6** into the **Secret** field.
5. Click **Add secret**.

> **Note:** Remember the exact name you gave this secret — you will need to enter it when running the workflow.

### Step 8 — Navigate to the Actions Tab

1. On your project's repo, click the **Actions** tab in the header navigation bar.

### Step 9 — Locate the Workflow

1. On the Actions page, in the left sidebar under **Actions**, locate and click **pull-project-tasks**.

> **Note:** This corresponds to the `.github/workflows/pull-project-tasks.yml` file you pushed to your repo in **Step 4**.

### Step 10 — Run the Workflow

1. On the **pull-project-tasks** workflow page, click the **Run workflow** dropdown on the right side of the page.
2. Fill in the input fields:
   - **The name of the GitHub Organization containing the project** — your org name
   - **The name of the GitHub Project to update** — the project name you created in **Step 5**
   - **The owner of the source repository** — should be prepopulated with `im-infomagnus`
   - **The name of the source repository** — should be prepopulated with `ms-code-with-engineering-playbook`
   - **The owner of the target repository** — your org or user that owns the target repo
   - **The name of the target repository** — your project's repo name
   - **The name of the secret containing the PAT** — the secret name you created in **Step 7** (e.g., `PLAYBOOK_PAT`)
3. Once all fields are filled in, click the green **Run workflow** button.

### Step 11 — Verify the Workflow Completes

1. The workflow should now be triggered and running. You can monitor its progress on the **Actions** tab.

> **Note:** This process may take 20 minutes or longer to complete.

### Step 12 — Confirm the Imported Issues

1. Once the workflow has completed successfully, navigate to the **Projects** tab in your repo to verify that the Issues/tasks have been imported to your Table or Board.
2. You can also find the imported Issues under the **Issues** tab of your repo.