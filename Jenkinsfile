pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/Shri135/PES2UG22CS544_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                // sh 'g++ main/hello.cpp -o main/output'
                echo "Building..."
                exit 1
            }
        }

        stage('Test') {
            steps {
                sh './main/output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}