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
                sh 'npm ci'
                sh 'nmp run build'
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
                sh 'npm --version'
                sh 'echo "Hi" > Hi'
                sh 'ls -l'
            }
        }
    }
}
