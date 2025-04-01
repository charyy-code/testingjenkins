pipeline {
    agent any

    parameters {
        choice(name: 'ENVIRONMENT', choices: ['dev', 'test', 'prod'], description: 'Select Environment')
        string(name: 'SERVICE_NAME', defaultValue: 'my-service', description: 'Enter Service Name')
    }

    stages {
        stage('Print Parameters') {
            steps {
                script {
                    echo "Selected Environment: ${params.ENVIRONMENT}"
                    echo "Service Name: ${params.SERVICE_NAME}"
                }
            }
        }

        stage('Simulate Deployment') {
            steps {
                script {
                    if (params.ENVIRONMENT == 'prod') {
                        echo "Deploying ${params.SERVICE_NAME} to PRODUCTION!"
                    } else {
                        echo "Deploying ${params.SERVICE_NAME} to ${params.ENVIRONMENT} environment."
                    }
                }
            }
        }

        stage('Post-Deployment Check') {
            steps {
                script {
                    def isSuccess = true // Simulating success

                    if (isSuccess) {
                        echo "Deployment Successful!"
                    } else {
                        error "Deployment Failed!"
                    }
                }
            }
        }
    }
}
