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
                sh 'docker container stop rest-ci'
                sh 'docker container rm rest-ci'
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
