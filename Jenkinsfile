pipeline {
    agent any

    environment {
        BUCKET = 'noel-devops-deploy'
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Noelsiby/devopsassign1.git'
            }
        }

        stage('Create ZIP') {
            steps {
                sh 'zip -r project.zip .'
            }
        }

        stage('Upload to S3') {
            steps {
                sh 'aws s3 cp project.zip s3://$BUCKET/'
            }
        }

        stage('Deploy with CodeDeploy') {
            steps {
                sh '''
                aws deploy create-deployment \
                --application-name noeldevopcodedeploy \
                --deployment-group-name noelCodeDeployServiceRole \
                --s3-location bucket=$BUCKET,key=project.zip,bundleType=zip
                '''
            }
        }
    }
}
