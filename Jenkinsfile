pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'git pull origin master'
        sh './gradlew build'
        sh './gradlew bootRun -Dserver.port=8090'
      }
    }
    stage('Test') {
      environment {
        CI = 'true'
      }
      steps {
        sh './gradlew test'
      }
    }
    stage('Validate') {
      steps {
        sh 'echo \'validate\''
      }
    }
    stage('Deploy') {
      steps {
        sh 'echo \'deploy\''
      }
    }
  }
}