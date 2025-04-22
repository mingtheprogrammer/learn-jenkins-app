pipeline {
    agent any
    stages {
        stage('Without Docker') {
            steps {
                sh '''
                echo "Without docker"
                ls -la
                touch container-with-nodocker.txt
                '''
            }
        }  // This closing brace was missing
        stage('With Docker') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                ls -la
                echo "With docker"
                touch container-withdocker.txt
                '''
            }    
        }
    }
}