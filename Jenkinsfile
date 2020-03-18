pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                sh '''
                  sh hello.sh
                    git symbolic-ref --short -q HEAD || git rev-parse --short HEAD
                    git checkout master 
                    git symbolic-ref --short -q HEAD || git rev-parse --short HEAD
                    cat .git/refs/remotes/origin
                '''
            }
            
      }
    }
}
