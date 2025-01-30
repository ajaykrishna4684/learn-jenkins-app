pipeline {
    agent any  // Global agent needed when using stage-specific agents

    stages {
        stage('Hello') {
            agent {
                docker {
                    image 'node:18-alpine'
                }
            }
            steps {
                echo 'Hello World'
                sh 'npm --version'
                sh 'echo "Hello" > Hello'
                sh 'ls -l'
            }
        }
        
        stage('Hi') {
            agent {
                docker {
                    image 'node:18-alpine'
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
