pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Preparacion') { 
            steps { 
                sh 'whoami' 
            }
        }

        stage('Construccion') {
            steps {
                sh 'docker pull nexpeque/docker_minecraft'
            }
        }

        stage('analisis') {
            steps {
                sh 'docker run -d -p 25565:25565 --name minecraft-advanced -v /home/daniel/world nexpeque/docker_minecraft:latest'
            }
        }

        stage('push') {
            steps {
                sh 'docker images ls'
            }
        }

        stage('despliegue') {
            steps {
                sh 'docker ps'
            }
        }

    }
}
