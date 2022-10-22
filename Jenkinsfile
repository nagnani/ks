node {

     stage('code clone') {
        git 'https://github.com/nagnani/ks.git'
    } 

      stage('mvn version') {
         sh 'mvn --version'
    }

      stage('code clean') {
         sh 'mvn clean'
    }

      stage('mvn validate') {
         sh 'mvn validate'
    }

      stage('mvn compile') {
         sh 'mvn compile'
    } 
 
         stage('mvn test') {
         sh 'mvn test'
    } 
 
         stage('mvn package') {
          sh 'mvn package'
    }  
}    

