pipeline {
    agent any
    environment {
        TOMCAT_URL = 'http://13.250.64.185:8080'
        TOMCAT_USER = 'admin'
        TOMCAT_PASSWORD = 'admin'
    }
    stages {
        stage('Build') {
            steps {
                sh 'echo "<html><body><h1>Testing Hello, World!</h1></body></html>" > index.html'
            }
        }
        stage('Deploy') {
            steps {
                sh "curl -v -u $TOMCAT_USER:$TOMCAT_PASSWORD --upload-file index.html $TOMCAT_URL/manager/text/deploy?path=/hello&update=true"
            }
        }
    }
}
