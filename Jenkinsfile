pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', 
                    credentialsId: 'github-token', 
                    url: 'https://github.com/ranatryambak/terraform-jenkins-setup.git'
            }
        }
        stage('Terraform Init') {
            steps {
                sh 'rm -rf .terraform .terraform.lock.hcl'  
                sh 'terraform init'
            }
        }
        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
