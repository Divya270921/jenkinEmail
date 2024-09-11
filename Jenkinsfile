pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Divya270921/jenkinEmail.git'
            }
        }
        stage('Run Script') {
            steps {
                sh './script.sh'
            }
        }
    }
    post {
        always {
            mail to: 'n.divyashree272000@gmail.com',
                 subject: "Jenkins Build #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                 body: """Build completed.
                 Check console output at ${env.BUILD_URL}"""
        }
    }
}
