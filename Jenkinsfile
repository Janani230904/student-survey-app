pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/Janani230904/student-survey-app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t student-survey-app .'
            }
        }

        stage('Docker Push') {
            steps {
                sh 'docker tag student-survey-app janani2309/student-survey-app'
                sh 'docker push janani2309/student-survey-app'
            }
        }
    }

    post {

        success {
            echo 'BUILD SUCCESS'
        }

        failure {
            echo 'BUILD FAILED'
        }
    }
}
