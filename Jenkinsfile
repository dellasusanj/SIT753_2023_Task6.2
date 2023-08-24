pipeline {
    agent any
    environment {
    DIRECTORY_PATH = 'C:/SIT753/Jenkins/SIT753_2023_Task5.1' 
    TESTING_ENVIRONMENT = 'TestEnv'
    PRODUCTION_ENVIRONMENT = 'ProdEnv'
    } 

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compiling the code and generating necessary artifacts"
            }
        }

        stage('Test') {
            steps {
                echo "Running unit tests"
                echo "Running integration tests"
            }
        }

        stage('Code Quality Check') {
            steps {
                echo "Checking the quality of the code"
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }

        stage('Approval') {
            steps {
                echo "Waiting for manual approval (sleeping for 10 seconds)..."
                sleep(time: 10, unit: 'SECONDS')
            }
        }

        stage('Deploy to Production') {
            steps {
                sleep(time: 5, unit: 'SECONDS')
                echo "Deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
