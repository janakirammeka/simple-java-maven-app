pipeline{
    agent{
        docker{
            image 'maven'
            args '-v $HOME/.m2:/root/.m2'
        }
    }
    stages{
        stage('Quality Gate Status Check'){
            steps{
                script{
                  withSonarQubeEnv('sonarserver'){ 
                      sh "mvn sonar:sonar" 
                      }
                   }
            }
        stage('Maven for install'){
            steps{
                script{
                   sh mvn clean install
                }
            }
        }
     }
    }
}
