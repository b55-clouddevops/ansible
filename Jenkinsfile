pipeline {
    agent any 
    
    environment {                                  // Pipeline Variables : All the stages of the pipeline can use it.
        SSH_CRED = credentials('SSH_CRED')
    }

    stages {
        stage('Performing a dry run') {
            steps {
                sh '''
                    env 
                    ansible-playbook robo-drurun.yml  -e ENV=${ENV} -e COMPONENT=${COMPONENT} -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW}  

                '''
            }
        }
    }
}