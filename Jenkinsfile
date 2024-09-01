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
                sh '/home/grras/slavedir/apache-maven-3.9.9/bin/mvn install'
            }
        }
        stage('DEPLOYMENT'){
            steps{
                sh 'cp target/CROCS.war /home/grras/slavedir/apache-tomcat-9.0.93/webapps'
            }
        }
    }
}
