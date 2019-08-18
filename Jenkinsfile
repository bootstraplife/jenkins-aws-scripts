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
                sh 'docker build -t testimage .'
                sh 'docker run -p 80:80 -d testimage'
            }
        }
    }
}
