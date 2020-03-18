pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                script {
                  def proc = 'git symbolic-ref --short -q HEAD || git rev-parse --short HEAD'.execute()   
                }
                print proc
                sh '''
                    sh hello.sh
                    git checkout master 
                    git symbolic-ref --short -q HEAD || git rev-parse --short HEAD
                    cat .git/refs/remotes/origin/master
                '''
            }
            
      }
    }
}
