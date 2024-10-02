pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                // Checkout your repository containing the Ansible playbook
                sh 'rm -rf ansible'
                sh 'git clone https://github.com/ibukun-oyedeji/ansible.git'
                
            }
        }


        stage('Run Ansible Playbook') {
            steps {
                // Run the Ansible playbook
                sh 'cd ansible'
                sh 'ls -la'
                sh 'ansible-playbook ../ibukun.yaml'
            }
        }
    }

    post {
        success {
            echo 'Playbook executed successfully!'
        }
        failure {
         
            echo 'Playbook execution failed.'
 
        }
        always {
            // Clean up the cloned repository
            cleanWs()
        } 
    }
}

