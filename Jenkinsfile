pipeline {
  agent any
  stages {
    stage('SCM'){
      checkout scm
    }
    stage('TEST'){
      steps {
        sh 'mvn clean install compile test'
      }
    }
  }
}
