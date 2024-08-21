#!groovy
pipeline {
  agent any
  stages {
    stage('Maven Install') {
      steps {
        sh 'docker run --rm -v $PWD:/app -v /root/.m2:/root/.m2 -w /app maven:3.5.0 mvn clean install'
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
