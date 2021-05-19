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
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}