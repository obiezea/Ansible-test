pipeline {
    agent any

    stages {
        stage('Clone Ansible Playbook') {
            steps {
                git branch: 'main', url: 'https://github.com/obiezea/ansible-test.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    credentialsId: 'ssh-user', 
                    installation: 'ansible', 
                    inventory: 'inventory', 
                    playbook: 'freestyle.yaml', 
                    become: true, 
                    becomeUser: 'root'
                )
            }
        }
    }
}
