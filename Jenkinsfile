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

        stage('build') {
          steps {
            sh 'mvn -Dmaven.test.failure.ignore=true clean package'
          }
        }
        stage('archive') {
          steps {
            archiveArtifacts 'target/*.jar'
          }
        }
        stage('test') {
          steps {
            junit '**/target/surefire-reports/TEST-*.xml'
          }
        }

      }
    }

  }
}
