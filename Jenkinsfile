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
                bat 'dotnet build'
            }
        }

        // Stage 3: Publish the project
        stage('Publish') {
            steps {
                bat 'dotnet publish -c Release -o ./publish'
            }
        }
    }

    // Poll SCM every 5 minutes
    triggers {
        pollSCM('H/5 * * * *')
    }
}