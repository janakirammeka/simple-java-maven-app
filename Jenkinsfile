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
                  withSonarQubeEnv('sonarserver'){ sh "mvn sonar:sonar" }
                      
                sh mvn clean install
                }
            }

        }
    }
}
