def app

def remote = [:]
remote.name = "dev-server"
remote.host = "newlinkedlist.xyz"
remote.allowAnyHosts = true

pipeline {
    agent { docker { image 'python:3.7.2' } }

    tools {nodejs "node"}

    stages {    
        stage('Clone repository') {
            steps {
                /* Let's make sure we have the repository cloned to our workspace */

                checkout scm
            }
        }
        
        stage('Test') {
            steps {
                sh 'python -m unittest'
            }
        }
    }
}