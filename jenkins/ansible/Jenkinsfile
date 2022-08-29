pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                git url: "https://github.com/sangramrath/vCard.git"
            }   
        }
        stage("execute Ansible") {
           steps {
                ansiblePlaybook credentialsId: 'root', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'hosts', playbook: 'nginx-playbook.yaml'
            }    
        }    
    }
}
