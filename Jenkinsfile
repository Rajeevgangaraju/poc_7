pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Rajeevgangaraju/poc_7.git'
            }
        }

        stage('Deploy Application') {
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
}
