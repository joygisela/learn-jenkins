pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'  // Correct node image
                    reuseNode true  // Allows reusing the workspace
                }
            }
            steps {
                script {
                    sh '''
                        ls -la
                        node --version
                        npm --version
                        npm ci
                        npm run build
                        ls -la
                    '''
                }
            }
        }
    }
}

