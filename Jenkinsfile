pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    ls -al
                    node --version
                    npm --version
                    npm ci
                    ls -al /home/node/.npm/_logs
                    cat /home/node/.npm/_logs/*.log
                    npm run build
                    ls -al
                '''
            }
        }
    }
}