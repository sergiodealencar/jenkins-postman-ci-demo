# Jenkins + Postman CI/CD Demo

This repository demonstrates how to automate API testing using a **Postman collection** executed by **Newman** inside a **Jenkins pipeline running on Docker**.

## Overview

- **Tools Used**:
  - [Jenkins](https://www.jenkins.io/) (Continuous Integration/Delivery)
  - [Postman](https://www.postman.com/) (API testing)
  - [Newman](https://www.npmjs.com/package/newman) (Postman CLI)
  - [Docker](https://www.docker.com/products/docker-desktop)

- **Pipeline Workflow**:
  1. Jenkins spins up in a Docker container.
  2. The pipeline installs Newman.
  3. It runs the Postman collection via Newman.
  4. A test report is generated and displayed in Jenkins.

## How to Run Locally

1. **Clone this repository:**
   ```bash
   git clone https://github.com/sergiodealencar/jenkins-postman-ci-demo.git
   cd jenkins-postman-ci-demo
   ```

2. **Jenkins installation (using [Docker](https://www.docker.com/products/docker-desktop))**
   ```bash
   docker run -p 8080:8080 -p 50000:50000 --restart=on-failure -v jenkins_home:/var/jenkins_home --env JAVA_OPTS="-Dfile.encoding=UTF8" vdespa/jenkins-postman
   ```

   If you are on Apple Silcon, use the following command:
   ```bash
   docker run --platform linux/amd64 -p 8080:8080 -p 50000:50000 --restart=on-failure -v jenkins_home:/var/jenkins_home --env JAVA_OPTS="-Dfile.encoding=UTF8" vdespa/jenkins-postman
   ```
   
3. **Local address to access Jenkins:**
   ```bash
   http://localhost:8080
   ```
   
4. **Steps to run Postman pipeline:**
   1. Click on "+ New Item"
   2. Enter an item name
   3. Select "Pipeline" and click on the [OK] button
   4. Past the following pipeline inside the Script window:
      
  
   ```bash
   pipeline {
    agent any

    stages {
        stage('Running Collection') {
            steps {
                sh '''
                    newman run https://api.postman.com/collections/46008687-2486952c-da6a-4f29-a6fc-d8de420e4b94?access_key=PMAT-01K3Y0YPXV81AEPN1R9WD98695 \
                    --reporters cli,htmlextra \
                    --reporter-htmlextra-export newman/report.html
                '''
                  }
              }
          }
      }
     ```
   
   
