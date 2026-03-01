pipeline {
    agent any

    stages {

        stage('GIT') {
            steps {
                echo "Getting Project from Git"
                git branch: 'main', url: 'https://github.com/BederSaad/devops'
            }
        }

        stage('MVN CLEAN') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('MVN COMPILE') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('MVN SONARQUBE') {
            steps {
                sh 'mvn sonar:sonar \
                    -Dsonar.host.url=http://192.168.33.10/:9000 \
                    -Dsonar.login=54f92d29f786c240c0b72791319f0cbdc5d344db'
            }
        }

    }
}
