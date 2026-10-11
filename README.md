# DevOps and Agile Interview Questions

Interview-level answers in simple English for BCA students, freshers, and entry-level full-stack and DevOps roles. Examples and practical scenarios are included where helpful.

## Agile and Azure DevOps

### 1. What is Azure Boards?

Azure Boards is the work-tracking service in Azure DevOps. Teams use it to plan, assign, prioritize, and track work throughout development.

It supports backlogs, Kanban boards, sprint planning, queries, and reporting. For example, a team might create a user story for a login feature, break it into tasks, assign those tasks to developers, and track their progress on a sprint board.

### 2. What is Jira?

Jira is a work-management and issue-tracking tool from Atlassian. Software teams commonly use it to manage backlogs, bugs, user stories, sprints, and Kanban boards.

For example, a team can use Jira to plan a two-week sprint, assign stories to developers, and track work from "To Do" through "Done." Jira can also integrate with tools such as Bitbucket, GitHub, and CI/CD services.

### 3. What is Trello?

Trello is a visual work-management tool based on boards, lists, and cards. A card represents a piece of work, and moving it between lists shows its progress.

For example, a simple board might have "Ideas," "In Progress," and "Done" lists. Trello works well for lightweight project tracking; teams with complex software workflows may need more specialized features from tools such as Jira or Azure Boards.

### 4. What are Agile work items such as Epic, Feature, User Story, Task, Bug, and Issue?

Work item names and hierarchy can vary by tool and process template. A common structure is:

- **Epic:** A large business objective that may take several releases or teams to complete. Example: "Improve the online shopping experience."
- **Feature:** A significant capability that contributes to an epic. Example: "Enable customers to save payment methods."
- **User story:** A user-focused requirement, often written as: "As a customer, I want to save a payment method so that checkout is faster."
- **Task:** A specific piece of work needed to implement or support a story. Example: "Add the payment-method API endpoint."
- **Bug:** A defect where the software does not behave as expected. Example: "Checkout fails when the postal code contains a space."
- **Issue:** A general term for a tracked concern, request, or problem. In Jira, "issue" is a broad term for tracked work; in Azure DevOps, "Issue" may be a specific work item type in some process templates.

A common hierarchy is **Epic -> Feature -> User Story -> Task**, with bugs tracked at a level that fits the team's process.

### 5. How do you organize work items on an Agile board?

Start by connecting work to a goal, then break it into manageable pieces:

1. Create epics for major outcomes and features for capabilities.
2. Write user stories that describe value from the user's perspective.
3. Add acceptance criteria so the team knows what "done" means.
4. Break stories into tasks when implementation work needs more detail.
5. Prioritize the backlog based on value, urgency, and dependencies.
6. Plan a realistic set of stories for the sprint, if using Scrum.
7. Track work through clear states such as "To Do," "In Progress," "Review," and "Done."
8. Update the board as work changes, and regularly review blocked or aging items.

Keep stories small enough to complete and verify within a sprint where possible. The board supports team discussion; it does not replace clarifying requirements and dependencies together.

### 6. What are Azure DevOps dashboards?

Azure DevOps dashboards are customizable pages that display project or team information using widgets. Teams use them to get a quick view of progress and project health.

Widgets can show items such as sprint burndown, work-item queries, build results, deployment status, and test results. For example, a team dashboard might show current sprint progress alongside recent pipeline failures.

### 7. What are Azure Pipelines, and how do you create a pipeline?

Azure Pipelines is the Azure DevOps service for automating build, test, and deployment workflows. A pipeline can validate code changes and, when configured, deploy the resulting application.

A typical setup is:

1. Store code in a supported repository, such as Azure Repos or GitHub.
2. Create a pipeline in Azure DevOps and select the repository.
3. Define the pipeline using the web interface or a YAML file, commonly `azure-pipelines.yml`.
4. Configure steps to install dependencies, build the project, and run tests.
5. Add deployment stages, environments, and any required approvals.
6. Run the pipeline and fix failures before relying on it for releases.

For example, a Node.js pipeline might install packages, run unit tests, build the app, and deploy it to a test environment after a successful build. Exact steps depend on the application and deployment target.

### 8. What are service connections, and how do you connect Azure DevOps to external services?

A service connection is a configured way for Azure Pipelines to authenticate to an external service. It lets a pipeline perform actions such as deploying to Azure, pushing an image to a container registry, or accessing another cloud provider.

An authorized project user typically goes to **Project settings -> Service connections**, chooses the service type, and configures its authentication. The team then grants pipeline access as appropriate and selects that connection in the pipeline.

Use the least privileges needed, protect credentials, and prefer secure identity-based authentication where supported. Do not put passwords, tokens, or client secrets directly in pipeline YAML.

## DevOps Concepts

### 9. What is GitOps?

GitOps is an approach to operating and deploying systems where Git is the source of truth for the desired system configuration. Changes are made through version-controlled files and reviewed like code.

A GitOps controller can compare the desired configuration in Git with the live environment and apply changes to bring the environment in line. This makes changes easier to review, trace, and roll back. GitOps is especially common for managing Kubernetes deployments, but the approach can be used for other infrastructure and configuration too.

### 10. What are the advantages and disadvantages of DevOps?

**Advantages:**

- Faster, more frequent delivery through automation.
- Earlier feedback from builds, tests, and monitoring.
- Better collaboration between development and operations.
- More consistent environments and releases.
- Improved ability to detect and recover from failures.

**Disadvantages and challenges:**

- It takes time and investment to change tools, processes, and team habits.
- Automation can spread mistakes quickly if it is not tested and controlled.
- Pipelines, cloud resources, and security controls require ongoing maintenance.
- Teams may need new skills in automation, monitoring, and infrastructure.
- Poorly managed delivery speed can increase operational risk rather than reduce it.

DevOps is not just a set of tools; it also involves shared responsibility and continuous improvement.

### 11. What is the role and importance of DevOps in full-stack development?

A full-stack application includes several connected parts, such as a user interface, backend services, and a database. DevOps helps teams build, test, release, and operate those parts reliably.

For example, a pipeline can test frontend and backend changes, create a deployable build, and release it to a test environment. Monitoring can then help the team identify problems after deployment. This shortens feedback loops and makes it easier to coordinate changes across the stack.

## Related Comparisons and Processes

### 12. What is the difference between Azure DevOps, Git, GitHub, and GitOps?

- **Git** is a distributed version-control system. It tracks changes to files, lets developers work in branches, and supports merging changes.
- **GitHub** is a platform for hosting Git repositories and collaborating on code. It also offers features such as pull requests, code reviews, issues, and automation.
- **Azure DevOps** is a suite of development services, including Azure Repos for Git repositories, Azure Boards for work tracking, Azure Pipelines for automation, and test and artifact-management capabilities.
- **GitOps** is a way of managing deployments and system configuration using Git as the source of truth. It is an operating practice, not a Git hosting product.

In short: **Git is the version-control tool; GitHub and Azure DevOps are platforms; GitOps is an approach to managing delivery and operations.**

### 13. What is the difference between Docker and containers? How do they help in DevOps?

A **container** is an isolated process environment that packages an application with the dependencies it needs. A **Docker image** is a packaged template used to create containers. **Docker** is a platform and set of tools commonly used to build, distribute, and run container images.

Containers help DevOps teams by making application environments more consistent across development, testing, and production. They can also make deployment and scaling easier. Containers share the host operating system's kernel, so they are not the same as full virtual machines, which run their own operating systems.

Docker is a popular container toolset, but container technology is not limited to Docker.

### 14. What is the DevOps process? How does it work, and what are the architectures of Azure DevOps and GitOps?

The DevOps process is a continuous cycle of planning, building, testing, releasing, deploying, operating, and monitoring software. Feedback from users, tests, and production monitoring informs the next set of changes.

A typical workflow looks like this:

1. Plan work in a backlog.
2. Commit code changes to version control.
3. Automatically build and test the changes.
4. Package an approved build.
5. Deploy it through controlled environments.
6. Monitor the application and respond to issues.
7. Use feedback to plan improvements.

**Azure DevOps architecture:** Azure DevOps provides connected services for planning, source control, automation, testing, and artifacts. A team can use Azure Boards for work items, Azure Repos or a connected GitHub repository for code, Azure Pipelines for build and deployment, and other services for testing and package management. Pipelines can deploy to Azure or other supported targets using configured agents, environments, and service connections.

**GitOps architecture:** A developer proposes a change to configuration or deployment files in Git. After review and merge, a GitOps controller running in or alongside the target environment reads the desired state from the repository and applies it. It continually compares desired state with live state and can reconcile differences. The controller needs suitable access to the repository and target environment, so those permissions and credentials must be managed securely.

These approaches can complement each other: Azure Pipelines can build and publish an application image, while a GitOps controller deploys that image based on configuration stored in Git.
