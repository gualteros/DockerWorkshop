pipeline {

    environment {
        imagename = "danielgualteros/minecraftserver"
        registryCredential = '317225a2-abc5-4a65-8dba-3bc5da38a6ed'
        dockerImage = ''}


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

            script {
                dockerImage = docker.build imagename
                //sh 'docker build -t minecraftserver .'
            }
        }

        stage('analisis') {
            steps {
                sh 'docker image ls'
            }
        }

        stage('push') {
            steps {
                docker.withRegistry( '', registryCredential ) {
                    dockerImage.push("$BUILD_NUMBER")
                    dockerImage.push('latest')}
                //sh 'docker push danielgualteros/minecraftserver:minecraftserver'
            }
        }

        stage('despliegue') {
            steps {
                sh 'docker run -d -p 25565:25565 --name minecraft-advanced -v /home/daniel/world imagename:latest'
                sh 'docker ps'
            }
        }



    }
}
