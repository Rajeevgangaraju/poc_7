pipeline {
    agent any

    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'False'
    }

    stages {

        stage('Checkout Source Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Rajeevgangaraju/poc_7.git'
            }
        }

        stage('Deploy Application using Ansible') {
            steps {
                sh '''
                ansible-playbook \
                  -i inventory.ini \
                  --private-key /var/lib/jenkins/.ssh/dockerrpoc7.pem \
                  deploy.yml
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Deployment completed successfully!'
        }
        failure {
            echo '❌ Deployment failed. Check console output.'
        }
    }
}

