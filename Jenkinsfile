pipeline {
    agent any
    stages {
        stage('Build'){
            steps{
                echo 'Building...'
                //slackSend color: "warning", message: "Building..."
                //sh './mvnw clean compile -e'

            }
            post {
                success {
                    echo 'Build Success'
                    slackSend color: "good", message: "Build Success"
                }
                failure {
                    echo 'Build Failed'
                    slackSend color: "danger", message: "Build Failed"
                }
            }
        }
    }
}
