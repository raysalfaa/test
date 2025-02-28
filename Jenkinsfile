pipeline {
    agent any

    environment {
        SONARQUBE_URL = 'http://localhost:9000'
        sonarHome=tool 'sonarQubeScanner'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/raysalfaa/test.git'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                
                withSonarQubeEnv('sonarQube') {
                    sh '''
                    ${sonarHome}/bin/sonar-scanner \
                        -Dsonar.projectKey=jenkinscanner \
                        -Dsonar.sources=. \
                        -Dsonar.language=py \
                        -Dsonar.python.version=3 \
                        -Dsonar.host.url=$SONARQUBE_URL
                    '''
                }
            }
        }

    }
}
