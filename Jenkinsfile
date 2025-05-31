pipeline {
  agent any
  stages {
    stage('gitcheckout') {
      steps {
        git -version
      }
    }
    stage('stage 2') {
      steps {
        sh 'echo "Hello World 2"'
      }
    }
    stage('stage 3') {
      steps {
        sh 'echo "Hello World 3"'
      }
    }
  }
}
