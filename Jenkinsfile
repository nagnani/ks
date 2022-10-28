pipeline {
  agent any
    tools {
        maven 'Maven 3.8.6'
    }
    stages {
        stage('git clone'){
            steps{
                git 'https://github.com/nagnani/ks.git'  
            }    
        } 
        stage('maven version') {
            steps{
                sh 'mvn --version'
            }
        }
        stage('maven clean') {
            steps{
                sh 'mvn clean'
            }
        }
        stage('sonar scan') {
         steps{ 
     sh 'mvn sonar:sonar -Dsonar.projectKey=demotoken -Dsonar.host.url=http://18.215.118.45:9000 -Dsonar.login=f5764043688d48ad7745ff496257e0f4d241dbe7'
           }
        }
	  stage('maven validate') {
            steps{
                sh 'mvn validate'
            }
        }
         stage('maven compile') {
            steps{
                sh 'mvn compile'
            }
        }
          stage('maven test') {
            steps{
                sh 'mvn test'
            }
        }
         stage('maven package') {
            steps{
                sh 'mvn package'
            }
        }
        stage('maven deploy') {
            steps{
                sh 'mvn deploy'
            }
        }
    }
}