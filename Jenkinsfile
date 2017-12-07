pipeline {
    agent { docker 'python:3.5.1' }
    stages {
        stage('Build') {
            steps {
                sh 'python simple.py'
            }
        }
        stage('Test') {
          steps {
            sh 'echo This is the test'
          }
        }
    }
}
