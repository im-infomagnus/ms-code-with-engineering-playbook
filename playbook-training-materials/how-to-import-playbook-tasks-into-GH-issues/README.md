# How to Import Playbook Tasks into GitHub Issues

This guide walks you through importing engineering playbook tasks into your project's GitHub repository as Issues. The workflow is run directly from the playbook repo — there is no need to copy any files into your own project. By the end, you'll have a full set of playbook tasks available in your repo's **Projects** board and **Issues** tab.

## Prerequisites

- You have access to the [InfoMagnus engineering playbook repo](https://github.com/im-infomagnus/ms-code-with-engineering-playbook)
- You have admin (or sufficient) permissions on your project's GitHub repository
- You have permissions to create a Personal Access Token (PAT) for your GitHub account

---

## Steps

### Step 1 — Create a GitHub Project

1. Navigate to the main page of your project's repo and click the **Projects** tab in the header navigation bar.
2. On the Projects page, click the green **Link a project** button, then select **New project**.
3. In the dialog that appears, select either **Table** or **Board** in the left sidebar (Table is recommended).
4. Give your project a name and click **Create project**.

> **Note:** This is the Project you will import Issues/tasks into. You will need to reference this project's name when running the workflow later.

### Step 2 — Create a Personal Access Token (PAT)

1. Click your **profile avatar** in the upper-right corner of GitHub and select **Settings** from the dropdown menu.
2. On the Settings page, scroll to the bottom of the left sidebar and click **Developer settings**.
3. In the left nav, expand **Personal access tokens** and select **Tokens (classic)**.
4. Click **Generate new token** > **Generate new token (classic)**.
5. Give your token a descriptive name (e.g., `playbook-import-token`) and configure the following scopes:
   - **repo** — Full control of private repositories ✅
   - **workflow** — Update GitHub Action workflows ✅
   - **project** — Full control of projects ✅
6. Click **Generate token** at the bottom of the page.
7. **Copy the token value immediately** — you will not be able to see it again after leaving this page.

> **Important:** If your organization uses SSO, you will also need to authorize the token for SSO. On the **Personal access tokens** page, find your token and click **Configure SSO**, then click **Authorize** next to your organization.

### Step 3 — Add the PAT as a Repository Secret in the Playbook Repo

The PAT must be stored as a secret in the **playbook repo** (not your project's repo), since that is where the workflow runs.

1. Navigate to the [playbook repo settings](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/settings) via the Setting tab and click **Secrets and variables** in the left sidebar, then select **Actions**.
2. Click the green **New repository secret** button.
3. Enter a **unique name** for the secret (e.g., `YOURNAME_PLAYBOOK_PAT`) and paste the token value you copied in **Step 2** into the **Secret** field. Use a name that is unique to you to avoid conflicts with other team members' secrets.
4. Click **Add secret**.

> **Note:** Remember the exact name you gave this secret — you will need to enter it when running the workflow. You will delete this secret after the import is complete (see **Step 8**).

### Step 4 — Navigate to the Workflow

1. Go directly to the workflow page:
   [https://github.com/im-infomagnus/ms-code-with-engineering-playbook/actions/workflows/pull-project-tasks.yml](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/actions/workflows/pull-project-tasks.yml)

### Step 5 — Run the Workflow

1. On the **pull-project-tasks** workflow page, click the **Run workflow** dropdown on the right side of the page.
2. Fill in the input fields:
   - **The name of the GitHub Organization containing the project** — your org name
   - **The name of the GitHub Project to update** — the project name you created in **Step 1**
   - **The owner of the source repository** — should be prepopulated with `im-infomagnus`
   - **The name of the source repository** — should be prepopulated with `ms-code-with-engineering-playbook`
   - **The owner of the target repository** — enter your **organization name** (not an individual user name)
   - **The name of the target repository** — your project's repo name
   - **The name of the secret containing the PAT** — the secret name you created in **Step 3** (e.g., `PLAYBOOK_PAT`)
3. Once all fields are filled in, click the green **Run workflow** button.

### Step 6 — Verify the Workflow Completes

1. The workflow should now be triggered and running. You can monitor its progress on the **Actions** tab.

> **Note:** This process may take 20 minutes or longer to complete.

### Step 7 — Confirm the Imported Issues

1. Once the workflow has completed successfully, navigate to the **Projects** tab in your repo to verify that the Issues/tasks have been imported to your Table or Board.
2. You can also find the imported Issues under the **Issues** tab of your repo.

### Step 8 — Delete the PAT Secret from the Playbook Repo

Once the Issues/tasks have been successfully imported, you should remove the secret you created in **Step 3** from the playbook repo.

1. Navigate to the [playbook repo settings](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/settings) and click **Secrets and variables** in the left sidebar, then select **Actions**.
2. Find the secret you created (e.g., `YOURNAME_PLAYBOOK_PAT`) and click the **Delete** button (trash icon) next to it.
3. Confirm the deletion.

> **Important:** Do not leave your PAT secret stored in the playbook repo after the import is complete. Removing it ensures that your token is not accessible to others who have access to the repo.

### Step 9 — Recommended Project View Settings

1. **Table view:** It is recommended to update the View settings (found towards the upper right of the screen, indicated by a cog/gear icon) to **Group by > Parent Issue**. This will organize the tasks under their respective parent issues for easier navigation.
2. **Board view:** It may be helpful to update the View settings to **Sort by > Parent Issue** to see which parent issue each task pertains to.