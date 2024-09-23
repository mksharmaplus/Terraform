#How to Install and Configure Jenkins on Amazon Linux 2023
#https://medium.com/@belek.bagishbekov/how-to-install-and-configure-jenkins-on-amazon-linux-2023-a8d7463a0404
# https://www.davidc.net/sites/default/subnets/subnets.html
# sudo mount -o remount,size=4G,noatime /tmp
 
==========================================================================================================================

#wget https://releases.hashicorp.com/terraform/1.3.7/terraform_1.3.7_linux_amd64.zip  terrform form 





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
