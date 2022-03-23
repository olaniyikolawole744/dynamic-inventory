pipeline {
    agent any

    environment {
        
        ANSIBLE_HOSTS="ansible/inventory/ec2.py"
        EC2_INI_PATH="ansible/inventory/ec2.ini"
        
    }

    stages {
        stage('PLAY ANSIBLE BOOK.') {
             steps {
                sh 'chmod 755 ansible/inventory/hosts/ec2.ini'
                sh 'chmod 755 ansible/inventory/hosts/ec2.py'
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook ansible/playbook/playbook.yml -i ansible/inventory/hosts/ec2.py' 
            }
        }   
    }
}