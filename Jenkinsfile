pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'make'
                    } else {
                        bat 'make'
                    }
                }
            }
        }

        stage('Permissions') {
            when {
                expression { isUnix() }
            }
            steps {
                script {
                    sh 'chmod +x ./StringInverser'
                }
            }
        }

        stage('Nettoyage') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'make clean'
                    } else {
                        bat 'make clean'
                    }
                }
            }
        }
    }
}
