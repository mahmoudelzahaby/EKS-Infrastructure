pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: 'master']], userRemoteConfigs: [[url: 'https://github.com/mahmouddahaby/Fixed-Solutions-Infrastructure']]])
            }
        }
        stage('Terraform Init') {
            steps {
                    sh 'terraform init'
            }
        }
        stage('Terraform Apply') {
            when {
                branch 'master'
            }
            steps {
                    sh 'terraform apply -auto-approve'
            }
        }
    }
}