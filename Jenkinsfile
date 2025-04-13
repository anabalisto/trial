pipeline {
    agent {
        label 'aws-ec2-agent'  // Matches the EC2 template label
    }
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/anabalisto/trial.git'
            }
        }
        stage('Build') {
            steps {
                sh 'echo "Running on dynamically provisioned EC2!"'
                sh 'java -version && docker --version'
            }
        }
    }
    post {
        always {
            cleanWs()  // Clean workspace after build
        }
    }
}
