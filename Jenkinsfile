pipeline {
    agent any
    
    stages {
        stage('Git') {
            steps {
                git branch: 'main', url: 'https://github.com/chandansoni99/Jenkins-Java-Project.git'
            }
        }
        stage('Build') {
            steps {
               withEnv(['PATH+EXTRA=/Users/chandan.soni01/Desktop/Software/apache-maven-3.3.9/bin']) {
                sh 'mvn clean compile'
                }
            }
        }
        stage('Test') {
            steps {
                withEnv(['PATH+EXTRA=/Users/chandan.soni01/Desktop/Software/apache-maven-3.3.9/bin']) {
                sh 'mvn test'
                }
            }
            post {
                always {
                    junit '**/target/surefire-reports/TEST-*.xml'
                }
            }
        }

    }
}
