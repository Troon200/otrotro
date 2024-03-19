pipeline {
    agent any
    stages {
        stage('Connection Git') {
            steps {
                git branch: 'main', url: 'https://github.com/Troon200/otrotro.git'
            }
        }
        stage('Test') {
            steps {
                echo "a las 2"
            }
        }
        stage('Connection prom') {
            steps {
                script {
                    def prometheusURL = 'http://10.195.146.2:9090'
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
