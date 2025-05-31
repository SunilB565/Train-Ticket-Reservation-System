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
    stages {
        stage('build') {
            steps {
                sh 'sudo yum update -y && sudo yum install -y java-1.8.0-openjdk maven git wget'
                sh 'cd Train-Ticket-Reservation-System && mvn clean install'
            }
        }
    }    
    stages {
        stage('deploy') {
            steps {
                sh '''
                wget https://dlcdn.apache.org/tomcat/tomcat-11/v11.0.6/bin/apache-tomcat-11.0.6.tar.gz && tar -xzvf apache-tomcat-11.0.6.tar.gz && rm -f apache-tomcat-11.0.6.tar.gz
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
