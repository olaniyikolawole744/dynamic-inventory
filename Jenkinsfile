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
                
               
                withCredentials([sshUserPrivateKey(credentialsId: '4e8fdb4d-d24c-42b5-af0f-0b302b9fbdba', keyFileVariable: 'password', usernameVariable: 'username')]) {
                
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook --u $username ansible/playbook/playbook.yml -i ansible/inventory/hosts/ec2.py -C -vvvvv' 
                 
                }  
            }
        }   
    }
}