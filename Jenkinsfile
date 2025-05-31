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
        stage('build') {
            steps {
                sh 'cd Train-Ticket-Reservation-System && mvn clean install'
            }
        } 
        stage('deploy') {
            steps {
                sh '''
                cp target/TrainBook-1.0.0-SNAPSHOT.war ../apache-tomcat-11.0.6/webapps/
                cd ../apache-tomcat-11.0.6/webapps
                rm -rf ROOT
                mv TrainBook-1.0.0-SNAPSHOT.war ROOT.war
                cd ../bin 
                chmod +x *.sh
                ./startup.sh
                '''
            }
        }        
    }
}
