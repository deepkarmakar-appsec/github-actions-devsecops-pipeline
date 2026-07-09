1. What is the purpose of this GitHub Actions workflow?

Answer: This workflow automatically runs a Trivy filesystem (FS) scan whenever code is pushed to the main branch.


---

2. What does name: Trivy Scan do?

Answer: It gives the workflow a readable name that appears in the GitHub Actions tab.


---

3. What does on: specify?

Answer: It defines the event that triggers the workflow.


---

4. What does push mean here?

Answer: The workflow starts automatically whenever code is pushed.


---

5. Why is branches: - main used?

Answer: It limits the workflow so it runs only when code is pushed to the main branch.


---

6. What is a job in GitHub Actions?

Answer: A job is a collection of steps executed on a runner.


---

7. Why is the job named trivy?

Answer: It is simply the job identifier. It can be any valid name.


---

8. What does runs-on: ubuntu-latest mean?

Answer: It tells GitHub to execute the job on the latest Ubuntu virtual machine.


---

9. What is a step in GitHub Actions?

Answer: A step is a single task executed within a job.


---

10. Why is the Checkout step required?

uses: actions/checkout@v3

Answer: It downloads the repository code onto the GitHub runner so later steps, like Trivy, can scan the project files.


---

11. What happens if the Checkout step is removed?

Answer: The repository code will not be available on the runner, so Trivy cannot scan the project files.


---

12. What does uses: mean?

Answer: It tells GitHub Actions to use an existing reusable action instead of writing commands manually.


---

13. What is aquasecurity/trivy-action@master?

Answer: It is the official GitHub Action used to run Trivy scans inside GitHub Actions.


---

14. What is the purpose of the with: section?

Answer: It passes configuration values (inputs) to the Trivy Action.


---

15. What does scan-type: fs mean?

Answer: It tells Trivy to perform a filesystem scan on the repository files.


---

16. What does format: table do?

Answer: It displays the scan results in a readable table format in the GitHub Actions logs.


---

17. Which branch triggers this workflow?

Answer: Only the main branch.


---

18. Where does this workflow run?

Answer: On a GitHub-hosted Ubuntu runner (ubuntu-latest).


---

19. In what order are the steps executed?

Answer:

1. Checkout the repository.


2. Run the Trivy filesystem scan.




---

20. Why must the Checkout step come before the Trivy scan?

Answer: Because Trivy needs access to the repository files. Without checking out the code first, there are no files available to scan.
