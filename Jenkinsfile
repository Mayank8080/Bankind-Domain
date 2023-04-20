pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Deploy') {
            steps {
                deploy adapters: [tomcat8()], authentication: [credentialsId: 'my-credentials-id'], contextPath: '/', war: 'target/myapp.war', url: 'http://localhost:9006'
            }
        }
    }
}
