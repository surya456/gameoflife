#!/usr/bin/env groovy
pipeline{
    agent{ label 'master' }
    stages{
       stage('git checkout'){
          steps{
             script{
                git credentialsId: 'git', url: 'https://github.com/GithubBijay/gameoflife.git'
             }
          }   
       }
        stage('Nexus Download'){
            steps{
                script{
                    withCredentials([usernamePassword(credentialsId: 'nexus', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                    sh 'curl -X GET -u $USER:$PASS http://3.15.152.128:8081/nexus/content/repositories/releases/be/cegeka/gameoflife/0.0.1/gameoflife-0.0.1.war -o $WORKSPACE/gameoflife-0.0.1.war' 
                    }
                }
            }   
        }
        stage('deploy'){
            steps{
                scripts{
                     sh 'ansible-playbook -i $WORKSAPCE/host $WORKSAPCE/gameoflife.yml --extra-vars $works=$WORKSPACE'
                }
            }
                
        }
    }
 }
          
                
