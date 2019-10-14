pipeline {
  agent {
    docker {
      image 'rawmind/alpine-jdk8'
      args 'mvn test'
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