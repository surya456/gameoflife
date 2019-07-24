#!/usr/bin/env groovy
pipeline{
    agent{ label 'master' }
    stages{
       stage{
          steps{
             script{
                git credentialsId: 'git', url: 'https://github.com/GithubBijay/gameoflife.git'
             }
          }   
       }
    }
 }
          
                
