pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: "https://github.com/jay-and-main/PES1UG22CS252_Jenkins.git"]]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS252-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post{
        failure{
            error 'Pipeline failed'
        }
    }
}