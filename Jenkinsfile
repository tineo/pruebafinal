pipeline {
    agent any

    environment {
        // Define variables de entorno aquí si las necesitas
        APP_NAME = "mi-app"
        ENVIRONMENT = "dev"
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Clonando el repositorio...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Iniciando la compilación...'
                // Comando para compilar el proyecto
                sh 'echo Compilando el proyecto...'
            }
        }

        stage('Test') {
            steps {
                echo 'Ejecutando pruebas...'
                // Comando para ejecutar pruebas
                sh 'echo Corriendo pruebas unitarias...'
            }
        }

        stage('Deploy') {
            when {
                branch 'main' // Solo desplegar en la rama main
            }
            steps {
                echo 'Desplegando la aplicación...'
                // Comando para desplegar la aplicación
                sh 'echo Desplegando a ${ENVIRONMENT}...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finalizado, limpiando recursos...'
            cleanWs() // Limpia el workspace después de cada ejecución
        }
        success {
            echo 'Pipeline ejecutado exitosamente!'
        }
        failure {
            echo 'El pipeline falló.'
        }
    }
}
