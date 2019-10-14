pipeline {
  agent {
    docker {
      image 'maven:3-jdk-8'
      args 'mvn compile'
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