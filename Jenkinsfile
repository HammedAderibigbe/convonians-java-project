pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp && mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcatpassword', path: '', url: 'http://3.87.7.236:8080/')], contextPath: 'my app', war: '**/*.war'
            }
        }
    }
}
