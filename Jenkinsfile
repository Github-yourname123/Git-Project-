#!/usr/bin/env groovy
 pipeline {
       agent any
       stages {
           stage('Build Image') {
               steps {
                   script {
                       docker.build("your-dockerhub-username/housing-prediction-app")
                   }
               }
           }
           stage('Publish Image') {
               steps {
                   script {
                       docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials-id') {
                           docker.image("your-dockerhub-username/housing-prediction-app").push("latest")
                       }
                   }
               }
           }
       }
   }
