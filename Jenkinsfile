pipeline {
        agent none 
        stages{
                stage('Docker'){
                        agent {
                            docker {
            
                             image 'maven:3-alpine' 
                             args '-v /root/.m2:/root/.m2' 
                            }
                        }
                        steps {
                        sh 'mvn -B -DskipTests clean package' 
                    }   
                }
        }
}
