pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        git --version
      }
    }
    stage('build') {
      steps {
        sudo apt update -y
        sudo apt install -y maven
        cd Train-Ticket-Reservation-System
        mvn clean install
      }
    }
    stage('stage 3') {
      steps {
        sh 'echo "Hello World 3"'
      }
    }
  }
}
