pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
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
            echo 'Post build condition running' // This action will happen regardless of the build result
        }
        failure {
            echo 'Post Action if Build failed' // This action will happen only if the build has failed
        }
    }
}
