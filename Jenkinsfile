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
                    cat /etc/resolv.conf
                    npm ping --registry=https://registry.npmjs.org/ --fetch-retries=0 --fetch-timeout=15000
                '''
            }
        }
    }
}