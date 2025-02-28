pipeline {
    agent any

    environment {
        SONARQUBE_URL = 'sonarQube'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/raysalfaa/test.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarQube') {
                    sh 'sonar-scanner'
                }
            }
        }
    }
}
