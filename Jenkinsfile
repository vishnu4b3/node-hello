pipeline {
    agent any
    stages {
    stage('Checkout project code') {
        steps {
            git branch: 'master',
                credentialsId: 'github_credentials',
                url: 'https://github.com/vishnu4b3/node-hello.git'
        }
    }

        stage('Build and push docker image') {
            steps {
                script {
                    sh 'cd /usr/local/bin/'
                    sh '/usr/local/bin/docker --version'
                    sh '/usr/local/bin/docker build -t pvishnu/node-hello:${BUILD_NUMBER} .'
                    sh '/usr/local/bin/docker push pvishnu/node-hello:${BUILD_NUMBER}'

                    }
                }
            }
        }
    }
