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
                        bat 'npm run test-suite-1'
                    }
                }

                stage('Testes no Electron') {
                    steps {
                        bat 'npm run test-suite-2'
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