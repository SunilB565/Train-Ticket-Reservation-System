pipeline {
  agent any
  stages {
    stage('Clone') {
      steps {
        git 'https://github.com/SunilB565/Train-Ticket-Reservation-System.git'
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
