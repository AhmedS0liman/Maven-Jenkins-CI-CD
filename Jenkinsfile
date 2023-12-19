pipeline {
    agent any

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
                sh 'docker-compose up -d'
            }
        }
    }
