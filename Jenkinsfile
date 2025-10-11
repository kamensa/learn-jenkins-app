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
                    ls -la
                    rm package-lock.json
                    npm install
                    node --version
                    npm --version
                    npm ci
                    #npm run build
                    ls -la node_modules/.bin/react-scripts/bin
                '''
            }
        }
    }
}
