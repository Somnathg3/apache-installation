
pipeline {
    agent any

    stages {

        stage('Update Server') {
            steps {
                sh 'sudo -n apt update -y'
            }
        }

        stage('Install Apache2') {
            steps {
                sh 'sudo -n apt install apache2 -y'
            }
        }

        stage('Start Apache2') {
            steps {
                sh 'sudo -n systemctl enable apache2'
                sh 'sudo -n systemctl start apache2'
            }
        }

        stage('Verify Apache2') {
            steps {
                sh 'sudo -n systemctl status apache2 --no-pager'
            }
        }
    }

    post {
        success {
            echo 'Apache2 installed successfully!'
        }

        failure {
            echo 'Apache2 installation failed!'
        }
    }
}
