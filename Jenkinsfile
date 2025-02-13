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
        export HOME=/var/lib/jenkins
        exec bash -c "npm ci"
                        ls -la
                '''
            }
        }
    }
}