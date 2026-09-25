The 6 questions + answers

1. What triggers this workflow to run?

The workflow is triggered by activity specified in the on: section of deploy.yml. It runs when changes are pushed to the repository and when a pull request is made against the repository. The workflow uses these events to automatically validate changes and, when appropriate, deploy the website.

2. What are the four main steps this workflow performs?

The workflow's main process can be summarized as:

Checkout code — retrieves the repository's code.
Build and test — validates the HTML and checks the website for broken links or other problems.
Configure the GitHub Pages environment — prepares the deployment environment and permissions.
Deploy to GitHub Pages — publishes the website when the required checks pass.

3. What does the "Checkout code" step do and why is it necessary?

The Checkout code step downloads the repository's current files into the GitHub Actions runner. This is necessary because the runner needs access to the project's HTML and other files before it can validate, test, or deploy the website.

4. What is the purpose of the environment configuration?

The environment configuration tells GitHub Actions where and how the website should be deployed. It establishes the GitHub Pages deployment environment and provides the permissions/settings needed for the workflow to publish the site.

5. How does this automated deployment improve reliability compared to manual deployment?

Automated deployment makes the process more consistent because the same validation and deployment steps are performed every time. The workflow checks the website before deployment, which helps catch HTML errors and broken links before they reach the live site. It also reduces the possibility of mistakes that can happen when deploying manually.

6. What would happen if you pushed code to a different branch (not main)?

The workflow can still run for the branch events specified in deploy.yml, such as a pull request. However, the actual GitHub Pages deployment is configured to occur from main, so simply pushing to another branch would not publish that branch as the live site. The branch can still go through the testing process before it is merged into main.