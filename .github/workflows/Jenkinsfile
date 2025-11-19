pipeline {
    agent any

    tools {
        nodejs "node-js24" // The NodeJS tool you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Since Git is already configured via Jenkins job, you can just checkout
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Project') {
            steps {
                sh 'npm run build'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}
