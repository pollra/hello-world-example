pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('build') {
      steps {
        withMaven(maven: 'M3') {
          sh 'mvn install:install-file "-DgroupId=org.mozilla" "-DartifactId=jss" "-Dversion=4.2.5" "-Dpackaging=jar" "-Dfile=C:\Users\AArmijos\workspace\componentes-1.0.4\deps\jss-4.2.5.jar"'
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
