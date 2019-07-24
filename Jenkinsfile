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
    }
 }
          
                
