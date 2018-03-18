pipeline {
  agent any
  stages {
    stage('Maven Build') {
      steps {
        sh '''sh \'./mvnw -B clean package\' 

stash name \'my-microservice-app\' includes: \'**/target/*.jar\''''
      }
    }
    stage('Run Unit Tests') {
      parallel {
        stage('Run Junit Tests') {
          steps {
            echo 'Starting Junit tests'
          }
        }
        stage('Check Code Coverage') {
          steps {
            sh 'sh \'./'
          }
        }
      }
    }
  }
}