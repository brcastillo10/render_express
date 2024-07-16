pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/brcastillo10/render_express.git'
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
                sh 'npm test'
            }
        }

        stage('Deploy') {
            steps {
                // Despliega el contenido a un servidor web o carpeta de despliegue
                sh 'scp -r ./dist user@server:/path/to/deploy' // ejemplo de despliegue usando SCP
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
