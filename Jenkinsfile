pipeline {
    agent any

    stages {
        stage('Frontend') {
            agent{docker{image 'node:14-alpine'}}
            steps {
                dir("DotnetTemplate.Web/") {
                    sh 'npm install'
                    sh 'npm run build'
                    sh 'npm run lint'
                    sh 'npm run test'

}    
                echo 'Building Frontend..'
            }
        }
        stage('Testing Backend') {
            agent{docker{image 'mcr.microsoft.com/dotnet/sdk:5.0'}}
            steps {
                sh 'dotnet build'
                sh 'dotnet test'
                echo 'Testing Backend'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}