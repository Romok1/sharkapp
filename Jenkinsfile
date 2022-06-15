pipeline {
   agent any
   //agent { 
     // docker { image 'ruby:3.1.0-bullseye' } 
   //}
   stages {
      stage('git repo & clean out') {
        steps {
           //sh "sudo rm -r sharkapp"
           //sh "git clone git@github.com:Romok1/sharkapp.git"
           sh "git branch -a"
           //sh "git checkout develop"
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
      //stage('Setting up OWASP ZAP docker container') {
      //      steps {
     //           script {
     //                   echo "Pulling up ruby "
     //                   sh 'docker pull ruby'
     //                  echo "Starting container --> Start"
     //                  sh """
    //                    docker run -dt --name myruby \
    //                     ruby \
    //                   /bin/bash
    //                   """
    //            }
    //         }
   //    }
      stage('Prepare wrk directory') {
             //when {
              //           environment name : 'GENERATE_REPORT', value: 'true'
             //}
             steps {
                 script {
                         sh """
                             docker exec myruby \
                             rm -r /home/testspace
                      
                             docker exec myruby \
                             mkdir /home/testspace
                         """
                     }
                 }
         }
      stage('change directory') {
             steps {
                 script {
                         sh """
                             docker exec myruby \
                             cd /home/testspace
                         """
                     }
                 }
         }
      stage('Git clone') {
             steps {
                 script {
                         sh """
                             docker exec myruby \
                             git clone git@github.com:Romok1/sharkapp.git
                         """
                     }
                 }
         }
      stage('Git list') {
             steps {
                 script {
                         sh """
                             docker exec myruby \
                             sh "ls -lart ./*"
                         """
                     }
                 }
         }
      stage('install') {
        steps {
          // dir('/var/lib/jenkins/workspace/githubcheckoutfirstpipe/sharkapp') {
               //sh '. ~/.bashrc'
               sh '#!/bin/bash -xl'
                 sh 'export PATH=$PATH:/var/lib/jenkins/.rvm/bin'
                 sh 'PATH=$PATH:$HOME/.rvm/bin'
                 sh '#!/bin/bash -l'
                 sh '/bin/bash --login'
                 sh 'set -x'
                 sh 'set -e'
                 //sh 'rvm use 3.1.0'
                //  sh "bundle install"
                 sh 'rvm use 3.1.0'
                 sh "bundle install" }
      }
      stage('Clone from Git') {
        steps {
            git branch: 'develop',
                url: 'git@github.com:Romok1/sharkapp.git'
        } 
      }
     //    catch (Exception ex) {
     //       println("Unable to git clone: ${ex}")
     //       error 'Git Clone failure'
   //     }
   }
}
