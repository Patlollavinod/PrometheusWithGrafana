pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Patlollavinod/PrometheusWithGrafana.git']])
            }
        }
        stage('Deploy with Ansible') {
            steps {
                 sshagent(['private-key']) {
                 "ssh ubuntu@172.31.39.67 ansible-playbook -i inventory playbook.yml"

      
                 }            
            }
        }
    }
}
