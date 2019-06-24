pipeline {
    agent {
        sh  'service docker start'
        sh  'sleep 10'
        sh  'service docker status'
        docker {
            
            image 'maven:3-alpine' 
            args '-v /root/.m2:/root/.m2' 
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
