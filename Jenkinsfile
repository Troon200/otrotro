pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "a las 1"
            }
        }
        stage('Test') {
            steps {
                echo "a las 2"
            }
        }
        stage('Deploy') {
            steps {
                script {
                    def prometheusURL = 'http://prometheus:9090'
                    def metricQuery = 'up'
                    def response = sh(script: "curl -s '${prometheusURL}/api/v1/query?query=${metricQuery}'", returnStdout: true).trim()
                    
                    echo "Prometheus Query Response: ${response}"
                    
                    // Realizar acciones basadas en la respuesta de Prometheus
                    // Por ejemplo, puede analizar la respuesta y tomar decisiones basadas en los valores recuperados.
                }
            }
        }
    }
}
