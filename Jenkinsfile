pipeline {
    agent any

    environment {
        SONARQUBE_URL = 'sonarQube'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/raysalfaa/test.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                def sonarHome=tool 'sonarQubeScanner';
                withSonarQubeEnv('sonarQube') {
                    sh '${sonarHome}/bin/sonar-scanner --version'
                }
            }
        }

    }
}
