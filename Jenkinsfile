pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/maven/apache-maven-3.8.3/bin"
    }
    stages{
       stage('GetCode'){
            steps{
                git 'https://github.com/sumit-mishra27/maven-devops.git'
            }
         }        
       stage('Build'){
            steps{
                sh 'mvn clean package'
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonarqube-8.9') { 
       
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
