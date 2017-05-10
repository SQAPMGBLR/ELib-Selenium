pipeline {
  agent any
  stages {
    stage('Checkout from SCM') {
      steps {
        git(url: 'https://github.com/SQAPMGBLR/ELib-Selenium.git', branch: 'master', changelog: true, credentialsId: 'sqapmgblr', poll: true)
        echo 'Build is done'
      }
    }
    stage('Sonar Reports') {
      steps {
        echo 'see reports'
        bat(script: 'sonar-scanner', returnStatus: true, returnStdout: true)
      }
    }
    stage('Selenium Test') {
      steps {
        echo 'Testing with selenium'
        bat '/SQAPMGBLR/ELib-Selenium/tree/master/src/com/nttdata/test java NewTest'
      }
    }
  }
}