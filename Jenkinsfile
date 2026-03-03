#!/user/bin/env groovy

pipeline {
  agent any

  tools {
    maven 'maven-jenkins-3.9.12'
  }

  stages {
    stage ('build jar') {
      steps {
        script {
          echo 'Building the Jar application'
          sh 'mvn clean package'
        }
      }
    }
    stage ('build image') {
      steps {
        script {
          echo 'Building Docker image'
          withCredentials([usernamePassword(credentialsId:'dockerhub-id', passwordVariable:'PASS', usernameVariable:'USER')]){
            sh '''
               docker build -t vetri18/java-1.0:1.0.0 .
               echo $PASS | docker login -u $USER --password-stdin
               docker push vetri18/java-1.0:1.0.0
            '''
          }
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
