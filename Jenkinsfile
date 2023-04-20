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
                deploy adapters: [tomcat8()], authentication: [credentialsId: '2b435cbe-343b-4a5a-8471-94f151003632'], contextPath: '/', war: 'target/myapp.war', url: 'http://localhost:9006'
            }
        }
    }
}
