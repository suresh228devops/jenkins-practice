pipeline {
    agent {
        label 'AGENT-1'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            echo 'This runs always after the build.'
            deleteDir()
        }
        success {
            echo 'Build successful!'
            // Add actions like deploying artifacts or sending success notifications
        }
        failure {
            echo 'Build failed!'
            // Add actions like sending failure alerts or triggering rollback
        }
    }
}
