pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'git pull origin master'
        sh './gradlew build'
        sh 'java -jar build/libs/spring-petclinic-2.1.0.BUILD-SNAPSHOT.jar  '
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