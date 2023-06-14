pipeline {
    agent none
    stages {
        stage('npm') {
            agent {
                docker {
                    image 'node:17-bullseye'
                }
            }
            steps {
                sh 'dir'
                sh 'node --version'
                sh 'cd ./DotnetTemplate.Web'
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage('.net') {
            environment { 
                DOTNET_CLI_HOME  = '/tmp/dotnet_cli_home'
                XDG_DATA_HOME = '/tmp'
            }
            agent {
                docker {
                    image 'mcr.microsoft.com/dotnet/sdk'
                }
            }
            steps {
                sh 'dir'
                sh 'dotnet build'
                sh 'dotnet test'
            }
        }
    }
}