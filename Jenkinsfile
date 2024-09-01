pipeline {
    agent {
  label 'blue'
        }
    environment{
        JAVA_HOME = '/home/grras/slavedir/jdk-11.0.23'
    }
triggers {
  pollSCM '* * * * *'
}


    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('BUILD'){
            steps{
                sh '/home/grras/slavedir/apache-maven-3.9.9/bin/mvn install'
            }
        }
        stage('DEPLOYMENT'){
            steps{
                sh 'cp target/CROCS.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
            }
        }
        stage('Notification'){
            steps{
                slackSend baseUrl: 'https://hooks.slack.com/services/', channel: '# crocs', color: 'good', message: 'Welcome To jenkins slack world ', teamDomain: 'DEVOPS', tokenCredentialId: 'SlackNotify'
            }
        }
    }
}
