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
                sh 'docker stop rest-ci'
                sh 'docker rm rest-ci'
                echo 'Build success...'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'docker run -d -v /home/zakichoiruddin24/apache-config-restci/:/etc/apache2/sites-enabled/ --name rest-ci -p 80:80 rest-ci-img'
                echo 'Deploy success...'
            }
        }
    }
}
