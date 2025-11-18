pipeline {
  agent any
  tools {
    maven 'Maven'
  }
  environment{
    NEW_VERSION = '1.3.0'
  }
  stages {
    stage('Build') {
      steps {
      echo 'Building..'
      // Here you can define commands for your build
      echo "Building ${NEW_VERSION}"
      bat "nvm install"
      }
    }
    stage('Test') {
      steps {       
        echo 'Testing..'
      // Here you can define commands for your tests
      }
    }
    stage('Deploy') {
      steps {
      echo 'Deploying....'
      // Here you can define commands for your deployment
      }
    }
  }
    post{

      always {
        echo 'Post build condition running'
      }
      failure {
        echo 'Post Action if build failed'
      }
      
    }
}
