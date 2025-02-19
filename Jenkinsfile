pipeline {
    agent any
    tools {
        nodejs "node23"
    }

    stages {
        stage("Installation") {
            steps {
                pnpm install
            }
        }
        stage("Build") {
            steps {
                pnpm build
            }
        }
        stage("Unit test") {
            steps {
                pnpm test
            }
        }
    }
}
