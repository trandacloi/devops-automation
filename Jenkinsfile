pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/trandacloi/devops-automation']])
                sh 'mvn clean install'
            }
        }
        stage('Build docker image') {
            steps{
               script{
                   sh'docker build -t lolloine/devops-integration.'
               } 
            }
        }
    }
}