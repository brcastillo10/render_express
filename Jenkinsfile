pipeline {
    agent any

    tools{
        nodejs "node"
    }

    stages {
        stage('Install') {
            steps {
                git branch: 'main', url: 'https://github.com/brcastillo10/render_express.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                // Añade cualquier paso de construcción necesario
                sh 'npm run build' // si tienes un script de construcción
            }
        }

        stage('Test') {
            steps {
                // Ejecuta los tests
                sh 'npm run test'
            }
        }

    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
