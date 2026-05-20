pipeline {
    agent any

    stages {

        stage('clone code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/UK9866/newrepo'
            }
        }

        stage('install packages') {
            steps {
                sh 'npm install'
            }
        }

        stage('test') {
            steps {
                sh 'npm test'
            }
        }

        stage('build images') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('deploy') {
            steps {
                sh 'docker run -d -p 80:2000 myapp'
            }
        }
    }
}
