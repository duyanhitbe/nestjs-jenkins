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
                    sh 'npm install'
                    sh 'npm run build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh 'npm run test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'pm2 start ecosystem.config.js'
                }
            }
        }

        stage('Send Message to Discord') {
            steps {
                script {
                    def discordWebhookUrl = 'https://discord.com/api/webhooks/1176785706698408008/kDnI6Sj1ixV3Gcc8nHzThSsTcUzRHLhGGBOCIVtQMOQ0ddSWkkpvZrcfGtC9hpkXJRTY'

                    def message = """
                        {
                            "content": "Hello, this is a message from Jenkins!"
                        }
                    """

                    sh """
                        curl -X POST -H "Content-Type: application/json" -d '${message}' ${discordWebhookUrl}
                    """
                }
            }
        }
    }
}
