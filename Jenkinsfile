#!groovy
pipeline {
  agent any
  stages {
    stage('Maven Install') {
      steps {
        sh '$PWD && ls -la'
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t grupo04/spring-petclinic:latest .'
      }
    }
  }
}
