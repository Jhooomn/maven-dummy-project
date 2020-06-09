pipeline {
  agent any
  stages {
    stage('TEST'){
      steps {
        sh 'mvn clean install compile test'
      }
    }
  }
}
