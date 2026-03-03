#!/user/bin/env groovy

pipeline {
  agent any

  tools {
    maven 'maven-jenkins-3.9.12'
  }

  stages {
    stage ('build') {
      steps {
        script {
          echo 'Building the application'
        }
      }
    }
    stage ('test') {
      steps {
        script {
          echo 'Testing the application'
        }
      }
    }
    stage ('deploy') {
      steps {
        script {
          echo 'Deploying the application'
        }
      }
    }
  }
}
