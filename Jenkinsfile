def flag = true

pipeline {
    agent any
    environment { // Add this block
        NEW_VERSION = '1.3.0' // Define your variable here
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                echo "Building version ${env.NEW_VERSION}" // Use the environment variable
            }
        }
        stage('Test') {
            when {
                expression {
                    return flag == false
                }
            }
            steps {
                echo 'Testing Project'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying Project'
            }
        }
    }
    post {
        always {
            echo 'Post build condition running'
        }
        failure {
            echo 'Post Action if Build failed'
        }
    }
}
