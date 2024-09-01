pipeline {
    agent {
  label 'blue'
        
    }


    stages {
        stage('checkout') {
            steps {
                checkout scm
            }
        }
        stage('BUILD'){
            steps{
                sh 'mvn install'
            }
        }
        stage('DEPLOYMENT'){
            steps{
                sh 'cp target/CROCS.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
            }
        }
    }
}
