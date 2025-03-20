pipeline {
    agent any
    environment {
    }
    // 1. I will get the source code from git
    // 2. I will build the docker image using docker build command, here I have to make sure that the Dockerfile exists
    // 3. I will run the docker image using docker run command on port 5000
    stages {
        stage('Get Source Code') {
            steps {
                git branch : 'main',
                url:'https://github.com/Tochi-Nwachukwu/jenkinsdocker.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    sh '''
                    cd jenkinsdocker
                    sudo docker build -t pythonapp .
                    '''
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    sh 'sudo docker run -p 5000:5000 pythonapp'
                }
            }
        }
    }
}
