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
                // sh 'firebase deploy --only hosting --finalexamtesting-33382 --token $FIREBASE_TOKEN'
            }
        }

        stage('Staging') {
            steps {
                echo 'Deploying to Staging...'
                // Add Firebase staging deployment command here
                sh 'firebase deploy --only hosting --finalexamstaging-66539 --token $FIREBASE_TOKEN'
            }
        }

        stage('Production') {
            steps {
                echo 'Deploying to Production...'
                // Add Firebase production deployment command here
                sh 'firebase deploy --only hosting --finalexamproduction-ea53b--token $FIREBASE_TOKEN'
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

