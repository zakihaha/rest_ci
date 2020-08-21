pipeline {
    agent any

    stages {
        stage('Check') {
            steps {
                sh 'ls'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker build -t coba-git .'
                sh 'docker container stop halo-rest'
                sh 'docker container rm halo-rest'
                sh 'docker run -d --name halo-rest -p 80:80 coba-git'
                sh 'docker ps'
                echo 'Deploy success....'
            }
        }
    }
}
