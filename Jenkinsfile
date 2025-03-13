pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url:"https://github.com/krishnakravi/PES1UG22CS294_Jenkins.git"]]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES1UG22CS294-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output3'
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
