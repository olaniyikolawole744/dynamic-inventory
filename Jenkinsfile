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
                sh 'pip install boto'
                sh 'ssh ec2-user@3.80.191.128'
                sh 'ssh ansible3.80.191.128@'
                sh 'ssh jenkins3.80.191.128@'
                sh 'ssh root@3.80.191.128'
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook --private-key /tmp/tf-packer -u ansible ansible/playbook/playbook.yml -i ansible/inventory/hosts/ec2.py' 
           
                 }
        }   
    }
}