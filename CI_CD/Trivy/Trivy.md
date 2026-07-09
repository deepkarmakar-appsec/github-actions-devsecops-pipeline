1. What is GitHub Actions?
Answer:
GitHub Actions is a CI/CD platform that automates software development workflows such as building, testing, security scanning, and deployment based on GitHub events.

2. What is a workflow?
Answer:
A workflow is an automated process defined in a YAML file inside .github/workflows/. It contains one or more jobs that execute when specific events occur.

3. What does `on` do in a workflow?
Answer:
The `on` keyword specifies the event that triggers the workflow, such as push, pull_request, schedule, or workflow_dispatch.

4. What is a job?
Answer:
A job is a collection of steps executed on the same runner. Multiple jobs can run sequentially or in parallel.

5. What is a GitHub runner?
Answer:
A GitHub runner is the machine that executes workflow jobs. It can be either a GitHub-hosted runner or a self-hosted runner.

6. What does `runs-on: ubuntu-latest` mean?
Answer:
It tells GitHub to create a temporary Ubuntu virtual machine and execute the job on it.

7. What is an ephemeral runner?
Answer:
An ephemeral runner is a temporary virtual machine created for a single workflow run. After the workflow finishes, the runner is automatically destroyed.

8. What are steps?
Answer:
Steps are individual tasks inside a job. They execute one after another in the order they are defined.

9. What is the difference between `uses` and `run`?
Answer:
- `uses` executes a reusable GitHub Action from GitHub Marketplace or another repository.
- `run` executes shell commands directly on the runner.

10. Why is `actions/checkout` required?
Answer:
It downloads the repository code onto the runner so that subsequent steps can access and work with the source code. Without it, the runner has no project files.

11. What does `with` do?
Answer:
The `with` keyword passes input parameters to a GitHub Action.

12. What is Trivy?
Answer:
Trivy is an open-source security scanner developed by Aqua Security. It scans file systems, dependencies, container images, Kubernetes resources, and repositories for vulnerabilities and security misconfigurations.

13. What does `scan-type: fs` mean?
Answer:
It tells Trivy to scan the project's file system, including source code and dependency files such as composer.lock, package-lock.json, and go.sum.

14. What does `format: table` do?
Answer:
It displays the scan results in a human-readable table format.

15. What vulnerabilities can Trivy detect?
Answer:
- Known CVEs
- Vulnerable dependencies
- Secrets (API keys, passwords, tokens)
- Misconfigurations
- License issues (when configured)

16. Where does Trivy get vulnerability information?
Answer:
Trivy downloads and updates its vulnerability database from trusted sources such as the National Vulnerability Database (NVD) and vendor security advisories.

17. What happens internally when this workflow runs?
Answer:
1. Code is pushed to GitHub.
2. GitHub detects the push event.
3. A temporary Ubuntu runner is created.
4. Repository code is checked out.
5. Trivy Action is downloaded.
6. Trivy scans the project.
7. Results are displayed in the workflow logs.
8. The runner is deleted automatically.

18. Why do we use security scanning in CI/CD?
Answer:
Security scanning helps detect vulnerabilities early in the software development lifecycle, allowing developers to fix issues before deployment and reducing security risks.

19. What is the difference between CI and CD?
Answer:
CI (Continuous Integration):
Automatically builds, tests, and scans code whenever changes are pushed.

CD (Continuous Delivery/Continuous Deployment):
Automatically delivers or deploys the application after successful CI checks.

20. Why is Trivy useful in DevSecOps?
Answer:
Trivy integrates security directly into the CI/CD pipeline, enabling developers to detect vulnerabilities before deployment. It supports the Shift-Left Security approach by making security testing part of the development process.
