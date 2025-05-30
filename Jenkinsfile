pipeline {
    agent any

    environment {
        GITHUB_CONTEXT = "Jenkins Build Status"
    }

    stages {
        stage('Build') {
            steps {
                echo 'Running build...'
                // Example build command
                // sh 'make build' or sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Example test command
                // sh 'make test' or sh 'mvn test'
            }
        }
    }

    post {
        success {
            script {
                githubNotify context: env.GITHUB_CONTEXT, status: 'SUCCESS', description: 'Build passed'
            }
        }
        failure {
            script {
                githubNotify context: env.GITHUB_CONTEXT, status: 'FAILURE', description: 'Build failed'
            }
        }
        unstable {
            script {
                githubNotify context: env.GITHUB_CONTEXT, status: 'FAILURE', description: 'Build unstable'
            }
        }
    }
}
