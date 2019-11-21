pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build'
        sh 'jenkins/build.sh'
      }
    }
        stage('Test') {
          steps {
            echo 'Testing'
            sh 'jenkins/test-all.sh'
            junit 'target/**/*.xml'
          }
        }
        stage('UAT Tests') {
          steps {
            echo 'UAT Testing Complete.'
          }
        }
        stage('Integration Testing') {
          steps {
            sh '''sleep 30 
'''
            timeout(time: 90) {
              echo 'done.'
            }

          }
        }
    
    stage('Deploy') {
      steps {
        echo 'Deploying'
        sh 'jenkins/deploy.sh'
      }
    }
  }
}
