
pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-east-1'
        S3_BUCKET = 'my-static-site-2026'
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/BandiRaviTheja/my-static-website.git'
            }
        }

        stage('Verify Files') {
            steps {
                sh 'ls -la'
            }
        }

        stage('Deploy to S3') {
            steps {

                withAWS(credentials: 'aws-credentials', region: 'us-east-1') {

                    sh '''
                    aws s3 sync . s3://$S3_BUCKET --delete \
                    --exclude ".git/*"
                    '''
                }
            }
        }
    }
}
