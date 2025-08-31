# Jenkins + Postman CI/CD Demo

This repository demonstrates how to automate API testing using a **Postman collection** executed by **Newman** inside a **Jenkins pipeline running on Docker**.

## Overview

- **Tools Used**:
  - [Jenkins](https://www.jenkins.io/) (Continuous Integration/Delivery)
  - [Postman](https://www.postman.com/) (API testing)
  - [Newman](https://www.npmjs.com/package/newman) (Postman CLI)
  - Docker & Docker Compose

- **Pipeline Workflow**:
  1. Jenkins spins up in a Docker container.
  2. The pipeline installs Newman.
  3. It runs the Postman collection via Newman.
  4. A test report is generated and displayed in Jenkins.

## How to Run Locally

1. **Clone this repository:**
   ```bash
   git clone https://github.com/your-username/jenkins-postman-ci-demo.git
   cd jenkins-postman-ci-demo
