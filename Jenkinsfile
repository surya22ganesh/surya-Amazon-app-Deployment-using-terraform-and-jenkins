pipeline {
    agent any

    stages {
        stage('clean workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage("Sonarqube analysis"){
            steps{
                sh ''' 
                    sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner
                '''
            }
        }
    }
}
