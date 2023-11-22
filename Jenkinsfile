pipeline {
    agent any
    
    environment {
        NODEJS_VERSION = '14.17.0'  // Update with your desired Node.js version
    }

    tool {
        Node18 = 'Node18'
    }

    stages {
        stage('Clone source') {
            steps {
                git branch: 'main', url: 'https://github.com/duyanhitbe/nestjs-jenkins.git'
            } 
        }
        stage('Install dependencies') {
            steps {
                sh 'yarn'
            }
        }
        stage('Build') {
            steps {
                sh 'yarn build'
            }
        }
        stage('Test') {
            steps {
                sh 'yarn test'
            }
        }
        stage('Run') {
            steps {
                sh 'yarn start:prod'
            }
        }
    }
}
