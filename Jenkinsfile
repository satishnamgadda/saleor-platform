 pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git url: "https://github.com/saleor/saleor-dashboard.git",
                    branch: "main"
            }
        }
        stage('build') {
            steps {
                sh 'sudo chmod 777 /var/run/docker.sock'
                sh 'docker info'
                sh 'docker image build -t satish1990/saleor-dashboard:dev-19122022 .'
                sh 'docker image push satish1990/saleor-dashboard:dev-19122022'
            }
        }
    }
}