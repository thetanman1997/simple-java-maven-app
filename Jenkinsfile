pipeline {
    agent none 
    stage('Pre Docker'){
                agent any 
                sh  'service docker start'
                sh  'sleep 10'
                sh  'service docker status'
    }
        stage('Docker'){
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
        }
    }
   }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
    }
}
