pipeline {
    agent any
    tools {
        maven "maven"
        jdk "JAVA_21"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mahmoudxdd/AteliersDevops.git'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package -Dmaven.test.skip=true"            }
        }
    }
}
