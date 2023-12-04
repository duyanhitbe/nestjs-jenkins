pipeline {
    agent any

    tools {
        nodejs "Node18"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    sh 'yarn'
                    sh 'yarn build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'yarn test'
                }
            }
        }
    }
}
