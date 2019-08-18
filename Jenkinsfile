pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Git checkout') {
            steps {
                
                checkout([$class: 'GitSCM',
                    branches: [[name: 'master']],
                    userRemoteConfigs: [[name: 'origin',
                                        url: 'https://github.com/bootstraplife/simple-node-js-react-npm-app.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                echo 'Building!'
                //check if docker is installed else install first
                // sh 'curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
                //     && tar xzvf docker-17.04.0-ce.tgz \
                //     && mv docker/docker /usr/local/bin \
                //     && rm -r docker docker-17.04.0-ce.tgz'
                sh 'sudo docker build -t testimage .'
                sh 'sudo docker run -p 80:80 testimage'
                // script {
                //     docker.build("testimage")
                // }
            }
        }
    }
}
