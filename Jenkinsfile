#!/usr/bin/env groovy
 pipeline {
       agent any
       stages {
           stage('Build Image') {
               steps {
                   script {
                       docker.build("githubyourname123/housing-prediction-app")
                   }
               }
           }
           stage('Publish Image') {
               steps {
                   script {
                       docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials-id') {
                           docker.image("githubyourname123/housing-prediction-app").push("latest")
                       }
                   }
               }
           }
       }
   }
