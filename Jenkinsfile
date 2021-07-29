pipeline {
    agent none
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
                    sh 'docker --version'
                    def dockerImage = docker.build("pvishnu/node-hello:master")
                    docker.withRegistry('', 'DockerHub_Credentials') {
                        dockerImage.push('master')
                    }
                }
            }
        }
 //       stage('Deploy to remote docker host') {
  //          environment {
   //             DOCKER_HOST_CREDENTIALS = credentials('DockerHub_Credentials')
     //       }
     //       steps {
     //           script {
//                     sh 'docker login -u $DOCKER_HOST_CREDENTIALS_USR -p $DOCKER_HOST_CREDENTIALS_PSW 127.0.0.1:2375//'
//                    sh 'docker pull antonml/node-demo:master'
  //                  sh 'docker stop node-demo'
    //                sh 'docker rm node-demo'
      //              sh 'docker rmi antonml/node-demo:current'
        //            sh 'docker tag antonml/node-demo:master antonml/node-demo:current'
          //          sh 'docker run -d --name node-demo -p 80:3000 antonml/node-demo:current'
            //    }
           // }
       // }
    }
}
