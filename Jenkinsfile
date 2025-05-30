pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
    }
    post {
        success {
            githubNotify context: 'CI', status: 'SUCCESS'
        }
        failure {
            githubNotify context: 'CI', status: 'FAILURE'
        }
    }
}
