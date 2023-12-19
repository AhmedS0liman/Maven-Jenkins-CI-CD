pipeline {
    agent any

    stages {
        stage('Build with Maven') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Move WAR File') {
            steps {
                sh 'mv target/*.war ./compose/sample.war'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh 'docker stack deploy -c ./compose/docker-compose.yml maven-cicd'
            }
        }
    }
}
