pipeline {
    agent any

    environment {
        
        ANSIBLE_HOSTS="inventory/ec2.py"
        EC2_INI_PATH="inventory/ec2.ini"
        
    }

    stages {
        stage('PLAY ANSIBLE BOOK') {
             steps {
                sh 'chmod 755 inventory/hosts/ec2.ini'
                sh 'chmod 755 inventory/hosts/ec2.py'
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook playbook/playbook.yml -i inventory/hosts/ec2.py 
            }
        }   
    }
}