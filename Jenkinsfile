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
                sh 'docker pull hello-world'
            }
        }

        stage('analisis') {
            steps {
                sh 'docker run hello-world'
            }
        }

        stage('push') {
            steps {
                sh 'docker images ls'
            }
        }

        stage('despliegue') {
            steps {
                sh 'make cpublishsas'
            }
        }

    }
}
