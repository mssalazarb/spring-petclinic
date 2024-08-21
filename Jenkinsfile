#!groovy

pipeline {
  agent none
  stages {
    stage('Maven Install') {
      agent {
        docker {
          image 'maven:3.5.0'
        }
      }
      steps {
        timeout(time: 20, unit: 'MINUTES') {
          sh 'mvn clean install'
        }
      }
    }
    stage('Docker Build') {
      agent any
      steps {
        sh 'docker build -t grupoxx/spring-petclinic:latest .'
      }
    }
  }
}
