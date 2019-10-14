pipeline {
  agent any
  stages {
    stage('Test') {
      agent {
        docker {
          image 'maven:3-jdk-8'
        }

      }
      steps {
        sh 'mvn test'
      }
    }
    stage('Package') {
      agent {
        docker {
          image 'maven:3-jdk-8'
        }

      }
      steps {
        sh 'mvn package'
        stash(name: 'Runner-jar', includes: 'target/**/*')
      }
    }
    stage('Docker') {
      agent any
      steps {
        unstash 'Runner-jar'
        sh 'docker build -f src/main/docker/Dockerfile.jvm -t quarkus/code-with-quarkus-jvm .'
      }
    }
  }
}