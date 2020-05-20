pipeline {
  agent any
  stages {
    stage('checkout project') {
      parallel {
        stage('checkout project') {
          steps {
            checkout scm
          }
        }

        stage('Declarative') {
          steps {
            sh 'mvn -Dmaven.test.failure.ignore=true clean package'
            archiveArtifacts 'target/*.jar'
            junit '**/target/surefire-reports/TEST-*.xml'
          }
        }

      }
    }

  }
}