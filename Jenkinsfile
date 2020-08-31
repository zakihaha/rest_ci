pipeline {
    agent any

    stages {
        stage('Check') {
            steps {
                sh 'ls'
            }
        }
        
        stage('Build') {
            steps {
                sh 'docker build -t rest-ci-img .'

                echo 'Build success...'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker run -d --name rest-ci -p 80:80 rest-ci-img'
                echo 'Deploy success...'
            }
        }
    }
}
