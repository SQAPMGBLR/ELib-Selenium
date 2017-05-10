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
  }
}