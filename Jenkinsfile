pipeline {
    agent any

environment {
    SELENIUM_URL = 'http://selenium:4444/wd/hub'
}
    tools {
        nodejs 'node20'
    }

    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

stage('Start App') {
    steps {
        sh 'node src/app.js &'
        sleep 5
    }
}


        stage('E2E') {
            steps {
                sh 'npm run test:e2e'
            }
        }
    }
}