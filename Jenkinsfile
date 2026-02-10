pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/BederSaad/devops.git'
            }
        }

        stage('Build Project') {
            steps {
                echo "Building Java project..."
                sh 'mvn clean package'
            }
        }

        stage('Run Application') {
            steps {
                echo "Running Java application..."
                sh 'java -jar target/*.jar'
            }
        }
    }

    post {
        success {
            echo "✅ Project executed successfully!"
        }
        failure {
            echo "❌ Build failed!"
        }
    }
}
