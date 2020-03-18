pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                sh '''
                  sh hello.sh
                  git branch
                '''
            }
            
      }
    }
}
