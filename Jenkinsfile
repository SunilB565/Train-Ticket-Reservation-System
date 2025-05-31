pipeline {
    agent any

    stages {
        stage('Checkout via SCM') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/master']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/SunilB565/Train-Ticket-Reservation-System.git',
                        // credentialsId: 'your-credentials-id'
                    ]]
                ])
            }
        }
    }
}
