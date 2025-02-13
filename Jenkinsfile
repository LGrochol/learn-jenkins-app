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
        cd /var/lib/jenkins/workspace/learn-jenkins-app
        npm config set cache /var/lib/jenkins/.npm
        npm config set userconfig /var/lib/jenkins/.npmrc
        npm ci
                        ls -la
                '''
            }
        }
    }
}