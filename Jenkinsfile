pipeline {
    agent any

    stages {
           stage('Clone Repository') {
               steps {
                   checkout([$class:'GitSCM',
                   branches: [[name: '*/main']],
                   userRemoteConfigs: [[url: "https://github.com/amulyap23/PES2UG21CS062_Jenkins.git']]])
               }
            }

        stage('Build') {
            steps {
                build 'PES2UG21CS062-1'
                sh 'g++ main.cpp -o output"
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed!'
        }

    }
}
