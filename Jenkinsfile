pipeline {
    agent any
    tools {
        node "node23"
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
