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
                echo 'docker image ls'
            }
        }

        stage('analisis') {
            steps {
                echo 'make cpublishsas'
            }
        }

        stage('push') {
            steps {
                echo 'make cpublishsas'
            }
        }

        stage('despliegue') {
            steps {
                echo 'make cpublishsas'
            }
        }

    }
}
