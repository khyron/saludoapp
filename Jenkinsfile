pipeline {
    agent any

    tools {
        maven 'Maven 3.8.6'
        jdk 'JDK21'
    }

    stages {
        stage('Clonar') {
            steps {
                git branch: 'main', url: 'https://github.com/khyron/saludoapp.git'
            }
        }

        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo '🎉 El build fue exitoso'
        }
        failure {
            echo '💥 El build falló'
        }
    }
}

