pipeline {
    agent any

    environment {
        SCANNER = 'SonarScanner'
    }

    stages {

        stage('Checkout') {
            steps {
                // If your code is local, this is fine
                checkout scm
            }
        }

        stage('SonarCloud SAST') {
            steps {
                withSonarQubeEnv('SonarCloud') {
                    sh """
                        sonar-scanner \
                        -Dsonar.projectKey=azan04_Lab11 \
                        -Dsonar.organization=azan04 \
                        -Dsonar.sources=. \
                        -Dsonar.host.url=https://sonarcloud.io
                    """
                }
            }
        }

        stage('Quality Gate') {
            steps {
                timeout(time: 2, unit: 'MINUTES') {
                    waitForQualityGate abortPipeline: true
                }
            }
        }

        stage('Build') {
            steps {
                echo "Build stage here"
            }
        }

    }
}
