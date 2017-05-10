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
        bat 'java -cp "https://github.com/SQAPMGBLR/ELib-Selenium/bin;https://github.com/SQAPMGBLR/ELib-Selenium/jar/*" org.testng.TestNG https://github.com/SQAPMGBLR/ELib-Selenium/testng.xml'
      }
    }
  }
}