pipeline {
  agent any
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
      steps {
        // requires SonarQube Scanner 2.8+
        withSonarQubeEnv('Sonarqube') {
          sh "${scannerHome}/bin/sonar-scanner"
        }
      }
    }
  }
}
