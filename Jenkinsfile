pipeline {
    agent any
     environment {
        AWS_ACCESS_KEY_ID     = credentials('aws_access_key')
        AWS_SECRET_ACCESS_KEY = credentials('aws_secret_key')
        AWS_DEFAULT_REGION     = "us-east-1"
    }
 
  
    stages {
        stage('Git Clone') {
            steps {
               git 'https://github.com/12-02-1991/Dev-Test-Prod-Env.git'
            }
        }
         stage('Terraform init') {
            steps {
             sh 'terraform init'
            }
        }
         stage('Terraform plan') {
            steps {
                 sh 'terraform plan'
            }
        }
        stage('Terraform apply') {
            steps {
                 sh 'terraform apply -auto-approve'
            }
        }
    }
}
