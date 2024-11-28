pipeline {
    agent {
        label 'master'
    }
    environment{
        SONAR_TOKEN='9b272d2b0107596def48d0769950c1bbe2c7d7ac' 
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    }
}
