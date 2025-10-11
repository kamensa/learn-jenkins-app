pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode false
                }
            }
            steps {
                sh '''
                    ls -la
                    rm package-lock.json
                    npm install
                    node --version
                    npm --version
                    npm ci
                    chown -R root:root .
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
