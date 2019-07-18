pipeline {
    agent any
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
    }
}

