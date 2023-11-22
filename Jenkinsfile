pipeline {
    agent any

    tools {
        nodejs = "Node18"
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
