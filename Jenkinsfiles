pipeline {
    agent any

    environment {
        PATH = "C:\\Windows\\System32:${env.PATH}"  // Add System32 path explicitly
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/MohitSingh9454/Mern-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t final_devops_project_image .'
            }
        }

        stage('Deploy using Docker Compose') {
            steps {
                bat 'docker-compose down || exit 0'
                bat 'docker-compose up -d --build'
            }
        }
    }
}
