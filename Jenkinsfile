pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    stages {

        stage('CHECKOUT') {
            steps {
                git 'https://github.com/knVeerendra/Demo.git'
            }
        }

        stage('BUILD') {
            steps {
                dir('demo') {
                    bat 'mvn clean install'
                }
            }
        }

        stage('TEST') {
            steps {
                dir('demo') {
                    bat 'mvn test'
                }
            }
        }
    }

    post {
        success {
            echo 'Build Successful'
        }
        failure {
            echo 'Build Failed'
        }
    }
}