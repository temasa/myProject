pipeline {
  agent { label 'slave1' }
  tools {
    maven 'M3'
  }
  stages {
    stage('checkout') {
      steps {
        git 'https://github.com/temasa/myProject.git'
      }
    }
    stage('Build') {
      steps {
        sh 'mvn clean compile'
      }
    }
    stage('Test') {
      steps {
        sh 'mvn test'
        junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }
  }
}
