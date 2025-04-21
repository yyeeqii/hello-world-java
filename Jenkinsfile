pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/AndySee04/hello-world-java'
            }
        }
        stage('Build') {
            steps {
                powershell 'gradle clean build'
                // bat 'gradle build'
            }
        }
        stage('Test') {
            steps {
                powershell 'gradle test'
                // bat 'gradle test'
            }
        }
        stage('Deploy') {
            steps {
                powershell 'java -jar build/libs/hello-world-javaV1.jar'
            }
        }
    }
    post {
        always {
            echo 'Cleaning up workspace'
            deleteDir() // Clean up the workspace after the build
        }
        success {
            echo 'Build successful!!!'
            // You could add notification steps here
        }
        failure {
            echo 'Build failed!'
            // You could add notification steps here
        }
    }
}
//testing
// testtt
// for test 2
