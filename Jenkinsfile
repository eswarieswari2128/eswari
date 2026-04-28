pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying Application...'
                bat 'docker build -t myapp .'
                bat 'docker run -d -p 8081:8080 myapp'
            }
        }
    }
}
