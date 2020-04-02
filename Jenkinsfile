pipeline{
    agent any
    triggers { cron('H/2 * * * *') }
    stages{
        stage("A"){
            steps{
                script {
                     env.branch_commit_id = sh(script: "git symbolic-ref --short -q HEAD || git rev-parse --short HEAD", returnStdout: true).trim()
                     env.master_commit_id = sh(script: "cat .git/refs/remotes/origin/master | cut -c -7", returnStdout: true).trim()
                }
                print branch_commit_id
                print master_commit_id
                sh '''
                    env
                    sh hello.sh
                    git checkout master 
                    git symbolic-ref --short -q HEAD || git rev-parse --short HEAD
                    cat .git/refs/remotes/origin/master
                '''
            }
            
      }
    }
}
