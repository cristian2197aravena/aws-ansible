pipeline{
    agent any
    stages {
        stage('Checkout'){
            steps{
                git 'https://github.com/cristian2197aravena/aws-ansible.git'
            }
        }
        stage('Execute Ansible'){
            steps{
                ansiblePlaybook credentialsId: '34.242.100.98', disableHostKeyChecking: true, installation: 'ansible2', inventory: 'dev.inv', playbook: 'unzip.yml'
            }
        }
    }
}