def flag = true

pipeline {
    parameters { // Add this block
        string(name: 'VERSION', defaultValue: '1.1.0', description: 'version to deploy on prod')
        choice(name: 'CHOICE_VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    agent any
    tools {
        maven 'Maven'
    }
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project'
                echo "Building version ${env.NEW_VERSION}"
                bat 'mvn --version'
            }
        }
        stage('Test') {
            when {
                expression {
                    return params.executeTests == true // Use the parameter here
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
