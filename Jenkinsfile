pipeline {
    agent {
      label 'worker'
    }
    options {
      timestamps()
      disableConcurrentBuilds()
    }
    stages {
      stage('Git Checkout') {
        steps {
          checkout scm
        }
      }
   stage('SonarQube analysis') {
  // requires SonarQube Scanner 2.8+
  def scannerHome = tool 'SonarQube Scanner 2.8';
  withSonarQubeEnv('Sonarqube') {
    sh "${scannerHome}/bin/sonar-scanner"
  }
}
    }
}
