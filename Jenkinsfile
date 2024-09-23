pipeline {
    agent any
    tools{
        terraform 'tera'
    }
    stages {
        stage('git checkout code') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mksharmaplus/Terraform.git']])
            }
        }
        
        stage('terraform init') {
            steps {
                sh 'terraform init'
            }
        }
        
        
      
        stage('terraform plan') {
            steps {
                sh 'terraform plan'
            }
        }
        
        
        stage('terraform apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        } 
        
    }
}
