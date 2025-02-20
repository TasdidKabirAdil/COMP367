 pipeline {
    agent any

    stages {
        // Stage 1: Checkout code
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR_USERNAME/comp367-webapp.git'
            }
        }

        // Stage 2: Build the project
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
    }

    // Poll SCM every 5 minutes
    triggers {
        pollSCM('H/5 * * * *')
    }
}
