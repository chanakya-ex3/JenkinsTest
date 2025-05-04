pipeline {
    agent any

    environment {
        IMAGE_NAME = "my-docker-app"
        COMPOSE_FILE = "docker-compose.yml"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/chanakya-ex3/JenkinsTest.git', branch: 'main'
            }
        }

        stage('Stop Existing Containers') {
            steps {
                script {
                    // Stop and remove existing containers if running
                    sh '''
                    docker-compose -f $COMPOSE_FILE down || true
                    '''
                }
            }
        }

        stage('Build and Start Containers with Docker Compose') {
            steps {
                script {
                    // Build and bring up the containers with docker-compose
                    sh '''
                    docker-compose -f $COMPOSE_FILE up --build -d
                    '''
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}
