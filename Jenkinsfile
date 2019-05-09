pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        withMaven(maven: 'M3') {
          sh '''mvn clean install
'''
        }

      }
    }
    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }
  }
}