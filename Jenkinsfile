pipeline {
  agent {
    docker {
      image 'maven:3-jdk-8'
    }

  }
  stages {
    stage('Test') {
      steps {
        sh 'mvn test'
        stash(name: 'Target', includes: '/target/*')
      }
    }
    stage('Java') {
      agent any
      steps {
        unstash 'Target'
        sh 'docker build src/main/docker/Dockerfile.jvm -t quarks:${GIT_COMMIT}'
      }
    }
  }
}