# Basic GitHub Workflow Explanation

This document provides a basic explanation of a GitHub Actions workflow configuration.

## Workflow Trigger

- **on: push**  
  The workflow is triggered whenever a push is made to any branch in the repository.  
  The `branches: - '*'` configuration means the workflow will run on pushes to **all branches**.

## Jobs

The workflow defines two separate jobs that run independently.

### Job: print_hello

- **runs-on: ubuntu-latest**  
  This job runs on the latest available Ubuntu runner provided by GitHub Actions.

- **Steps**:
  - **Run a shell command:**  
    The command `echo "Hello World"` is executed, which simply prints "Hello World" to the output.  
    This step serves as a basic example of executing a command within a job.

### Job: run_tests

- **runs-on: ubuntu-latest**  
  Similar to the previous job, this job also runs on the latest Ubuntu runner.

- **Steps**:
  - **Run tests:**  
    The command `npm test` is executed. This assumes you have a Node.js project with tests defined in your `package.json`.  
    Running this command will execute your project's test suite.

## Summary

- **Trigger:** The workflow is activated on every push to any branch.
- **Jobs:**  
  - The first job (`print_hello`) prints a simple message to the console.
  - The second job (`run_tests`) runs the test suite for your Node.js project.
  
This basic setup demonstrates how you can automate tasks in your repository using GitHub Actions. You can expand on this configuration by adding more jobs or steps as your project's needs evolve.
