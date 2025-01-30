pipeline {
    agent any  // Global agent needed when using stage-specific agents

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                sh 'ls -l'
                sh 'npm ci'
                sh 'npm run build'
                sh 'ls -l'
            }
        }
        
        stage('Hi') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Hi'
                sh 'ls -l'
                sh 'npm --version'
            }
        }
    }
}
