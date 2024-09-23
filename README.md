# Project2-Compose

# AWS Elastic Beanstalk Express.js Sample Application

This is a sample **Node.js (Express)** application designed for deployment on **AWS Elastic Beanstalk**. It demonstrates the basic structure of a Node.js app and includes the setup for Continuous Integration/Continuous Deployment (CI/CD) using **Jenkins**.

## Table of Contents

- [Project Overview](#project-overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Jenkins CI/CD Pipeline](#jenkins-ci-cd-pipeline)
- [Running Tests](#running-tests)
- [Security Scans](#security-scans)
- [License](#license)

## Project Overview

This project is a simple **Express.js** application that can be deployed to **AWS Elastic Beanstalk**. It is also configured with a **Jenkins pipeline** for CI/CD, including dependency installation, security scanning using **Snyk**, and running tests.

## Prerequisites

Before you begin, ensure you have the following installed:

- [Node.js](https://nodejs.org/) (version 16 or higher)
- [NPM](https://www.npmjs.com/) (comes with Node.js)
- [Docker](https://www.docker.com/) (for running the Jenkins pipeline)
- [Jenkins](https://www.jenkins.io/) (optional for local CI/CD)

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/muhammadhaider49/aws-elastic-beanstalk-express-js-sample.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd aws-elastic-beanstalk-express-js-sample
   ```

3. **Install dependencies**:
   ```bash
   npm install
   ```

## Running the Application

To run the application locally, execute:

```bash
npm start
```

This will start the application on **port 3000**. You can access it by navigating to `http://localhost:3000` in your web browser.

## Jenkins CI/CD Pipeline

This project includes a **Jenkins pipeline** to automate CI/CD tasks. The pipeline consists of the following stages:

1. **Install Dependencies**: Installs all required Node.js dependencies using `npm install`.
2. **Install Snyk**: Installs **Snyk**, a tool for monitoring vulnerabilities in dependencies.
3. **Snyk Security Scan**: Runs a security scan on project dependencies using `snyk test`.
4. **Run Tests**: Executes any available tests (currently a placeholder script).
5. **Post Actions**: Logs the result of the build, indicating whether it succeeded or failed.

### Running the Jenkins Pipeline

To run the Jenkins pipeline:
1. Make sure Jenkins is set up with the pipeline definition from the `Jenkinsfile`.
2. The pipeline will automatically trigger builds when changes are pushed to the repository.

## Running Tests

Currently, this project does not have any unit tests defined. However, the **Jenkinsfile** includes a placeholder `test` script:

```bash
npm test
```

This script currently outputs `'No tests specified'`. You can add your own tests to the `scripts` section of `package.json` as needed.

## Security Scans

This project uses **Snyk** for security scanning. During the Jenkins pipeline, Snyk automatically checks for vulnerabilities in the dependencies.

To run the Snyk security scan locally, use:

```bash
snyk test
```

If you haven't installed Snyk yet, you can install it globally using:

```bash
npm install -g snyk
```

You will need to authenticate with Snyk using:

```bash
snyk auth
```

