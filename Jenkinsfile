pipeline {
    agent any
    stages {
        // Stage 1: Clone repository
        stage('Clone repository') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/ShadowKnight91/PES1UG21CS719_JENKINS']]
                ])
            }
        }

        // Stage 2: Build
        stage('Build') {
            steps {
                script {
                    build 'PES1UG21CS719-1'
                    sh 'g++ first.cpp -o output'
                }
            }
        }

        // Stage 3: Test
        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }

        // Stage 4: Deploy
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment steps here
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
