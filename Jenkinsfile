pipeline {
    agent any

    environment {
        CONTAINER_IMAGE  = 'expressapi_image' // Replace with your Docker Hub credentials ID
        CONTAINER_NAME   = 'expressapi_container'
        PORT             = '4000'
    }

    stages {
        stage('clone_repository') {
            steps {
                echo 'Cloning..'
                // cloning the repository
                git branch: 'main', url: 'https://github.com/mohsinakhtaralam/napp.git'
                
            }
        }
        stage('Build Docket Image') {
            steps {
                echo 'Docker Image Creating...'
                // create docker image
                sh 'docker build -t $CONTAINER_IMAGE .'
            }
        }
        stage('stop and delete old container') {
            steps {
                echo 'Stopping and Deleting old container...'
                // stop and delete old container
                sh 'docker stop $CONTAINER_NAME || true'
                sh 'docker rm $CONTAINER_NAME || true'
            }
        }
        stage('start new container') {
            steps {
                echo 'Starting Container...'
                // start new container
                sh 'docker run -d -p $PORT:$PORT --name $CONTAINER_NAME $CONTAINER_IMAGE'
            }
        }
    }
}
