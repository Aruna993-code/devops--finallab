pipeline {
    agent any

    environment {
        FIREBASE_TOKEN = credentials('firebase-token') // Store Firebase token in Jenkins credentials
    }

    stages {
        stage('Build') {
            steps {
                echo 'Installing Firebase CLI tools...'
                sh 'npm install -g firebase-tools'  // Install Firebase tools
            }
        }

        stage('Testing') {
            steps {
                echo 'Running tests...'
                // Add your test commands here, e.g., run unit tests or integration tests
            }
        }

        stage('Staging') {
            steps {
                echo 'Deploying to Staging...'
                // Add Firebase staging deployment command here
                sh 'firebase deploy --only hosting --project your-staging-project-id --token $FIREBASE_TOKEN'
            }
        }

        stage('Production') {
            steps {
                echo 'Deploying to Production...'
                // Add Firebase production deployment command here
                sh 'firebase deploy --only hosting --project your-production-project-id --token $FIREBASE_TOKEN'
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully.'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}

