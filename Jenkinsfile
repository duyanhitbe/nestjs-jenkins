pipeline {
    agent any
    tools {
        nodejs "node23"
    }

    stages {
        stage("Installation") {
            steps {
                sh 'pnpm install'
            }
        }
        stage("Build") {
            steps {
                sh 'pnpm build'
            }
        }
        stage("Unit test") {
            steps {
                sh 'pnpm test'
            }
        }
        stage("E2E test") {
            steps {
                sh 'pnpm test:e2e'
            }
        }
    }
}
