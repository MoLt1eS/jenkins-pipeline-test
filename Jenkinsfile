pipeline {
  agent {
    docker {
      args 'mvn test'
      image 'maven:3-jdk-8'
    }

  }
  stages {
    stage('Test') {
      steps {
        sh 'mvn test'
      }
    }
  }
}