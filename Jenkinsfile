pipeline {
    agent any
   
    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }

    stages {
        stage('Execucao') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                sh 'echo "Pipeline executada"'
            }
        }
      stage('Rodando a imagem') {
         agent {
            docker { image 'node:7-alpine' }
          }
        stages {
            stage('Test') {
                steps {
                    sh 'node --version'
                }
            }
        }
      }
      stage('Mostar variaveis de ambiente'){
         steps {
                sh 'printenv'
            }
      }
    }
   post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}

