pipeline {
    agent {
        label 'AGENT-1'
    }

    environment {
        COURSE = 'Jenkins'
    }

    options {
        timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuilds()
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh """
                        echo 'Building...'
                        sleep 10
                        echo "Course Name is: $COURSE"
                        env
                    """
                }
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
        }
        failure {
            echo 'Build failed!'
        }
    }
}
