pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo "Cloning repository from GitHub..."
                git branch: 'main', url: 'https://github.com/BederSaad/devops.git'
            }
        }

        stage('Build Project') {
            steps {
                echo "Building Java project..."
                sh "mvn clean package -Dmaven.test.skip=true"
            }
        }

        stage('Run Application') {
            steps {
                echo "Running Java application..."
                sh "java -jar target/*.jar"
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
