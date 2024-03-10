pipeline {
    agent any

    environment {
        // Définir le nom de votre image Docker ici
        DOCKER_IMAGE = 'App-backend:v1.0.0'
    }

    stages {
        stage('Initialisation') {
            steps {
                echo 'Démarrage du pipeline...'
            }
        }
        stage('Build et Dockerisation') {
            steps {
                echo 'Construction et Dockerisation de l\'application...'
                // Construire l'image Docker à partir du Dockerfile situé à la racine du projet
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
    }
    post {
        success {
            echo 'Image Docker construite avec succès.'
            echo 'Utilisez "docker run -p 80:80 $DOCKER_IMAGE" pour lancer l\'application.'
        }
        failure {
            echo 'La construction de l\'image Docker a échoué.'
        }
    }
}
