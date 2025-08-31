pipeline {
    agent any
    stages {
        stage('Install Newman') {
            steps {
                sh 'npm install -g newman'
            }
        }
        stage('Running Collection') {
            steps {
                sh 'newman run ???'
            }
        }
    }
}
