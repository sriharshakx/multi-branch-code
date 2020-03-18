pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                script {
                     env.branch_commit_id = sh(script: "git symbolic-ref --short -q HEAD || git rev-parse --short HEAD", returnStdout: true).trim()
                     env.master_commit_id = sh(script: "cat .git/refs/remotes/origin/master", returnStdout: true).trim()
                }
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
