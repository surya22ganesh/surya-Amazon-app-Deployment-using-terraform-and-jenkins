pipeline {
    agent any
    environment {
        SCANNER_HOME='/opt/sonarscanner/sonarscanner/bin/'
    }

    stages {
        // stage('clean workspace'){
        //     steps{
        //         cleanWs()
        //     }
        // }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage("Sonarqube analysis"){
            steps{
                sh ''' 
                    echo $SCANNER_HOME    
                    sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner
                '''
            }
        }
    }
}
