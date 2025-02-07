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
                    sh 'chmod +x ./mon_binaire'  // Remplacer 'mon_binaire' par le nom réel de ton exécutable
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
