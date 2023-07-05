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
                deploy adapters: [tomcat9(credentialsId: 'tomcatpassword', path: '', url: 'http://52.42.109.119:8080/')], contextPath: 'myapp', war: '**/*.war'
            }
        }
        
 
    }
}
