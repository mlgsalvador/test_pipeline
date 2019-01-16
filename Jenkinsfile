pipeline {
    agent { label 'aws' }
    stages {
        stage('Clone Repo') {
            steps {
                cleanWs()
                git credentialsId: 'gerrit-id', url: 'http://gerrit@10.0.3.210/gerrit/build-suite'
            }
        }

        stage('Build') {
            steps {
               sh '''npm install
               grunt build --project=sfra-sample
               '''    
            }
        }
    }
}
