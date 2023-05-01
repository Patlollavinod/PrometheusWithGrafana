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
                 sh "ls"
                 sh "ansible-playbook -i ineventory.yml playbook.yml"

      
                 }            
            }
        }
}
