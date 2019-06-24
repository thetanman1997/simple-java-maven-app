pipeline {
        agent none 
        stages{
                stage('pre docker'){
                agent any 
                    steps{
                            sh  'service docker start'
                            sh  'sleep 10'
                            sh  'service docker status'
                    }
                }

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
