pipeline{
    agent any
    environment {
        AWS_DEFAULT_REGION="us-west-2"
        THE_BUTLER_SAYS_SO=credentials('jenkins-git-ssh')
    }
    stages {
        stage('SCM Checkout'){
            steps{
                git credentialsId: '34.242.100.98', url: 'https://github.com/cristian2197aravena/aws-ansible.git'
            }
        }
        
        stage('test'){
        input {
            message "Should we continue"
            ok "Yes, we should"
            submitter "alice,bob"
            parameters {
                string(name: 'HOST', defaultValue: '0.0.0.0/0', description: 'Maquina conectarse')
            }
        }
        steps {
            echo "Hello, maquina ${HOST} SALUD"
        }
    }
            stage('Execute Ansible'){
            steps{
                ansiblePlaybook credentialsId: '34.242.100.98', disableHostKeyChecking: true, installation: 'ansible2', inventory: 'dev.inv', playbook: 'unzip.yml'
            }
        }
}
}