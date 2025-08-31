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
                sh 'newman run https://api.postman.com/collections/46008687-2486952c-da6a-4f29-a6fc-d8de420e4b94?access_key=PMAT-01K3Y0YPXV81AEPN1R9WD98695'
            }
        }
    }
}
