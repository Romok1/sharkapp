pipeline {
   agent any
   stages {
    stage('Checkout') {
      steps {
        script {
           sh 'echo "seen"'
           // The below will clone your repo and will be checked out to master branch by default.
           // git credentialsId: 'jenkins-user-github', url: 'git@github.com:Romok1/sharkapp.git'
           // Do a ls -lart to view all the files are cloned. It will be clonned. This is just for you to be sure about it.
           // sh "ls -lart ./*" 
           // List all branches in your repo. 
           //dir('/var/lib/jenkins/workspace/${env.JOB_NAME}) {
           //git clone -b develop git@github.com:Romok1/sharkapp.git
           //sh "git branch -a"
           // Checkout to a specific branch in your repo.
           //sh "git checkout staging"
           //sh 'git pull'
           //sh 'git merge'
           }
          }
       }
    }
  }
}
