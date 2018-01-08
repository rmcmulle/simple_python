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
              echo "STAGE_NAME should be 'Test': ${STAGE_NAME}"
          }
        }
        stage('Prepare for delivery') {
          when {
            branch 'development'
          }
          steps {
            sh 'echo Beginning to deliver...'
            input message: 'Would you like to proceed with build?'
            sh 'echo Continuing with the build...'
          }
        }
        stage('Prepare to deploy in production') {
          when {
            branch 'production'
          }
          steps {
            sh 'echo Now deploying to production...'
          }
        }
        stage('Cleanup') {
          steps {
            sh 'echo Cleaning up the build...'
          }
        }
    }
}
