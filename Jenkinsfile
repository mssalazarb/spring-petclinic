#!groovy

pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'maven:3.5.0'
          reuseNode true
        }
      }
      steps {
        sh 'mvn clean install -B -X'
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
