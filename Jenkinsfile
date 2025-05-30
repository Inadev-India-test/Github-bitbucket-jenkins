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
            echo 'Pipeline succeeded!'
            githubStatus(
                context: 'jenkins/build',
                description: 'Build passed',
                status: 'SUCCESS'
            )
        }
        failure {
            echo 'Pipeline failed!'
            githubStatus(
                context: 'jenkins/build',
                description: 'Build failed',
                status: 'FAILURE'
            )
            currentBuild.result = 'FAILURE'
        }
    }
}
