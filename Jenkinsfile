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
        stage('Prepare for delivery') {
          steps {
            sh 'echo Beginning to deliver...'
            input message: 'Would you like to proceed with build?'
            sh 'echo Continuing with the build...'
          }
        }
        stage('Cleanup') {
          steps {
            sh 'echo Cleaning up the build...'
          }
        }
    }
}
