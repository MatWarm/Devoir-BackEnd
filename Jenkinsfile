pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'app-backend:v1.0.1'
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
                sh 'whoami'
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
