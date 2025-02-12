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
                    node --version
                    npm --version
                    rm -rf node_modules
                    npm cache clean --force
                    export HOME=/var/lib/jenkins
                    npm config set userconfig /var/lib/jenkins/.npmrc
                    npm config set cache /var/lib/jenkins/.npm
                    npm config get userconfig
                    ls -la /var/lib/jenkins/workspace/learn-jenkins-app
                    npm config get cache
                    ls -la
                '''
            }
        }
    }
}