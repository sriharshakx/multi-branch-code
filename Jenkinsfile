pipeline{
    agent any
    stages{
        stage("A"){
            steps{
                script {
                     env.disk_size = sh(script: "df / --output=avail | tail -1", returnStdout: true).trim()
                  //def proc = 'git symbolic-ref --short -q HEAD || git rev-parse --short HEAD'.execute()   
                }
                print disk_size
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
