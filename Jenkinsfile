pipeline {
    agent none
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:17-bullseye'
                }
            }
            steps {
                sh 'dir'
                sh 'node --version'
            }
        }
        stage('.net') {
            agent {
                docker {
                    image 'mcr.microsoft.com/dotnet/sdk'
                }
            }
            steps {
                sh 'dir'
                sh 'dotnet build'
            }
        }
    }
}