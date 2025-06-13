def flag = true

pipeline {
    agent any
    tools { // Add this block
        maven 'Maven' // 'Maven' must match the name you configured in Jenkins Tools
    }
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                echo "Building version ${env.NEW_VERSION}"
                // Use a simple Maven command to show it's working
                bat 'mvn --version' // Use 'bat' for Windows commands
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
