pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'Jenkins Pipeline Working Successfully'
            }
        }

        stage('Verify Files') {
            steps {
                sh 'ls -la'
            }
        }
    }
}
