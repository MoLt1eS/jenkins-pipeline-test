pipeline {
  agent {
    docker {
      args 'mvn test'
      image 'quay.io/quarkus/centos-quarkus-maven:19.1.1'
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