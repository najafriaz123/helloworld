// Add this line at the very top of your Jenkinsfile
def flag = true // or false, depending on if you want it to run initially

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            when {
                expression {
                    return flag == false // Change this to 'true' if you want it to run, 'false' to skip
                }
            }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
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
