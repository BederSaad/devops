pipeline {
    agent any
    tools {
        maven "maven"
    }
    environment {
        JAVA_HOME = "/usr/lib/jvm/java-17-openjdk" // replace with your JDK path
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/BederSaad/devops'
            }
        }
        stage('Build') {
            steps {
                sh "mvn clean package -Dmaven.test.skip=true"
            }
        }
    }
}
