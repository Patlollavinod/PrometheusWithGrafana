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
                 
                  sh "ssh -o StrictHostKeyChecking=no ubuntu@65.0.104.111 ansible-playbook -i inventory playbook.yml"   

      
                 }            
            }
        }
    }
}
