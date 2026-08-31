pipeline {
    agent any

    stages {
        stage('Instalação das dependencias') {
            steps {
                bat 'npm install'
            }
        }

        stage('Execução dos testes') {
            steps {
                bat 'npm test'
            }
        }
    }

    post {
        success {
            echo 'Build e testes executados com sucesso'
        }
        failure {
            echo 'Falha na execução do pipeline'
        }
    }    



}