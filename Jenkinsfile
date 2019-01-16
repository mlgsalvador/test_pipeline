pipeline {
    agent { label 'aws' }
    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Clone Repo') {
            steps {
               git credentialsId: 'gerrit-id', url: 'http://gerrit@10.0.3.210/gerrit/build-suite'
               sh '''npm install
               grunt build --project=sfra-sample
               '''    
            }
        }
    }
}
