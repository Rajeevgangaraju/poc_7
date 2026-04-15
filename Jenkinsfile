pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git url: 'https://github.com/Rajeevgangaraju/poc_7.git', branch: 'main'
            }
        }
        stage('Deploy Application') {
            steps {
                sh 'ansible-playbook -i inventory.ini --private-key dockerrpoc7.pem deploy.yml'
            }
        }
    }
}
