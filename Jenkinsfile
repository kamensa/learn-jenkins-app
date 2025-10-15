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
                    #mkdir test.test
                    #node --version
                    #npm --version
                    npm ci react-scripts --save
                    npm run build
                '''
            }
        }
/*
        stage('Test') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }

            steps {
                sh '''
                    ls -la
                    #test -f build/index.html
                    #npm test
                '''
            }
        }
*/      
    }
}
