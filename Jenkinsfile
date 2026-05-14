pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning GitHub Repository'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Application'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application with AWS CodeDeploy'
            }
        }
    }
}
