pipeline {
    agent any

    tools {
        terraform 'Terraform-1.5'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/ranatryambak/terraform-jenkins-setup.git'
            }
        }

        stage('Terraform Init') {
            steps {
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
