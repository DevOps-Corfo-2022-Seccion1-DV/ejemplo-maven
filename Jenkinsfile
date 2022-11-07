pipeline {
    agent any
    stages {
        stage('Build'){
            steps{
                slackSend color: "warning", message: "Comenzando build"
                sh './mvnw clean compile -e'
            }
        }
        stage('Test'){
            steps{
                slackSend color: "warning", message: "Comenzando test"
		sh './mvnw clean test -e'
            }
        }
        stage('Package'){
            steps{
                slackSend color: "warning", message: "Comenzando package"
		sh './mvnw clean package -e’
            }
        }
        stage('Run'){
            steps{
                slackSend color: "warning", message: "Comenzando run"
		sh './mvnw spring-boot:run'
            }
        }
    }
    post {
        success {
            slackSend color: "good", message: "El Pipeline ha terminado con éxito"
        }
        failure { 
            slackSend color: "danger", message: "El Pipeline ha fallado"
        }
    }
}
