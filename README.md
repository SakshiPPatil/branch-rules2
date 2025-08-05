# branch-rules2

**Add branch protection rule to protect main branch:** <br/>
1) Require a pull request before merging: <br/>
2) Require approvals: When enabled, pull requests targeting a matching branch require a number of approvals and no changes requested before they can be merged. <br/>
3) Require conversation resolution before merging: If any conversation is marked as "Unresolved", the PR cannot be merged. <br/>

4) Require linear history: When you enable "Require linear history":
```
    👉 Only commits with a linear history can be pushed to protected branches (like main).
    👉 Merge commits are not allowed.
```

5) Require deployments to succeed before merging

```
📍 What it means:
When you enable “Require deployments to succeed before merging”:

👉 The pull request cannot be merged until the required deployment is successful.
👉 This ensures that your code is properly deployed and validated in an environment before merging to the protected branch.

⚙️ Typical Example:
You have GitHub Actions / Jenkins / any CI/CD pipeline that:

Builds your code

Runs tests

Deploys to a staging or test environment

👉 GitHub won’t allow the PR to be merged until that deployment completes successfully.

```

6) Require status checks to pass before merging

```
📌 What it means:
When this setting is enabled:

🚫 Pull requests cannot be merged into a protected branch (like main) unless all required status checks complete successfully.

🔍 What is a "status check"?
A status check is a result from an automated system like:

✅ GitHub Actions

✅ Jenkins

✅ CircleCI

✅ Travis CI

✅ Linting tools (like ESLint)

✅ Testing tools (like Jest, JUnit)

Each time a contributor opens a PR or pushes new code, these tools run and report their status back to GitHub.

✅ Success = Pass

❌ Failure = Blocked

⏳ Pending = Still running

```



create CODEOWNER file inside .github repo   and provide the name of the codeowner in it. so only codeowner merge the pull request.

<img width="1589" height="631" alt="image" src="https://github.com/user-attachments/assets/f2c3c2d7-42a9-4433-bf18-f37a79cb9535" />






