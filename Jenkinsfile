 
pipeline {
  agent any
  def rtMaven = Artifactory.newMavenBuild()
  stages {
    stage('SCM'){
     steps {
      checkout scm
     }
    }
   stage('Artifactory configuration') {
        // Tool name from Jenkins configuration
        rtMaven.tool = "Maven-3.3.9"
        // Set Artifactory repositories for dependencies resolution and artifacts deployment.
        rtMaven.deployer releaseRepo:'libs-release-local', snapshotRepo:'libs-snapshot-local', server: server
        rtMaven.resolver releaseRepo:'libs-release', snapshotRepo:'libs-snapshot', server: server
    }
    stage('TEST'){
      steps {
        sh 'mvn clean install compile test'
      }
    }
  }
}
