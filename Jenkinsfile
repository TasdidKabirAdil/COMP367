pipeline {
    agent any

    stages {
        // Stage 1: Checkout code
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/TasdidKabirAdil/COMP367.git'
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