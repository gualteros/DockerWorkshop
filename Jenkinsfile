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
                echo 'docker pull hello-world'
            }
        }

        stage('analisis') {
            steps {
                echo 'docker run hello-world'
            }
        }

        stage('push') {
            steps {
                echo 'docker images ls'
            }
        }

        stage('despliegue') {
            steps {
                echo 'make cpublishsas'
            }
        }

    }
}
