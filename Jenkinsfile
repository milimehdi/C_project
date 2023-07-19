pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Récupérer le code à partir du référentiel GitHub
                git 'https://github.com/milimehdi/C_project.git'
            }
        }
        stage('Build') {
            steps {
                // Compiler le programme main.c avec Gradle
                bat "gradle clean build"
            }
        }
        stage('Run') {
            steps {
                // Exécuter le programme main.c
                sh './build/exe/main'
            }
        }
    }
    post {
        always {
            // Nettoyer les fichiers temporaires ou effectuer des tâches de post-traitement si nécessaire
            cleanWs()
        }
    }
}