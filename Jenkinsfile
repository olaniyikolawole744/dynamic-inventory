pipeline {
    agent any

    environment {
        
        ANSIBLE_HOSTS="inventory/ec2.py"
        EC2_INI_PATH="inventory/ec2.ini"
        
    }

    stages {
        stage('CHANGE OWNERSHIP') {
             steps {
                sh 'chmod 755 inventory/hosts/ec2.ini'
                sh 'chmod 755 inventory/hosts/ec2.py'
             }
        }  

        stage('PLAY ANSIBLE BOOK') {
             steps {
                withCredentials([sshUserPrivateKey(credentialsId: '554b9cec-008e-4236-aec9-ac5b71c618b6', keyFileVariable: 'private_key', usernameVariable: 'username')]) {
                sh 'ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook --u $username --private-key $private_key playbook/playbook.yml -i inventory/hosts/ec2.py' 
                }
            }
        }   
    }
}


