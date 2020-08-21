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
                echo 'Deploy success....'
            }
        }
    }
}
