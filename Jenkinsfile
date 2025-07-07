pipeline {
  agent any

  environment {
    TF_WORKING_DIR = 'envs/dev'
  }

  stages {
    stage('Checkout Code') {
      steps {
        git url: 'git@github.com:ritesh4automation/terraform-infra.git', branch: 'main'
      }
    }

    stage('Terraform Init') {
      steps {
        dir("${env.TF_WORKING_DIR}") {
          sh 'terraform init'
        }
      }
    }

    stage('Terraform Validate') {
      steps {
        dir("${env.TF_WORKING_DIR}") {
          sh 'terraform validate'
        }
      }
    }

    stage('Terraform Plan') {
      steps {
        dir("${env.TF_WORKING_DIR}") {
          sh 'terraform plan'
        }
      }
    }
  }
}