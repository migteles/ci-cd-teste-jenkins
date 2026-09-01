pipeline {
    agent any

    stages {
        stage('Instalação das dependencias') {
            steps {
                echo 'Instalando node...'
                bat 'npm install'
            }
        }

        stage('Execução dos testes') {
            parallel {
                stage('Testes no chrome') {
                    steps {
                        bat 'npx run test-chrome'
                    }
                }

                stage('Testes no Electron') {
                    steps {
                        bat 'npx run test'
                    }
                }

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