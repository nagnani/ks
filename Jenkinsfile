pipeline {
  agent any
    environment {
         PATH="$PATH:/opt/maven"
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
            withSonarQubeEnv('sonarqube-8.9')
                sh "mvn sonar:sonar"
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