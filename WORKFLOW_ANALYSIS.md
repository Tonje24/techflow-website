# Workflow Analysis

## 1. What triggers this workflow to run?
The workflow runs when code is pushed to the main branch, or when a pull request is made to the main branch.

## 2. What are the four main steps this workflow performs?
1. Checkout code
2. Validate HTML
3. Check links
4. Upload artifact

## 3. What does the "Checkout code" step do and why is it necessary?
It downloads the code from the repository onto the computer that runs the workflow. This is necessary because that computer starts out empty, so the other steps would have no files to work with.

## 4. What is the purpose of the environment configuration?
It sets up the github-pages environment, so GitHub knows where to publish the website and can show the link to the live site.

GitHub also keeps a history of every deployment, which I can see under Deployments in the repository.

## 5. How does this automated deployment improve reliability compared to manual deployment?
The same steps run in the same order every time, so nobody forgets a step. The HTML and links are checked before the site goes live, and the site is only deployed if the checks pass. This means fewer mistakes than deploying by hand.

## 6. What would happen if you pushed code to a different branch (not main)?
The site would not be deployed. The deploy job only runs for pushes to main. On a pull request, the tests run but the deploy step is skipped. This happened with my feature branches.