pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'whoami' 
            }
        }

        stage('Deploy') {
            steps {
                sh 'make publish'
            }
        }
    }
}