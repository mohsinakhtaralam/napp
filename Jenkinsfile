pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // copy your build steps here
                sh 'echo "Build step executed"'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add your test steps here
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add your deploy steps here
            }
        }
    }
}