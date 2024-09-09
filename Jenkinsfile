pipeline {
    agent any
    environment {
        SCANNER_HOME='/opt/sonarscanner/sonarscanner'
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
        // stage("Sonarqube analysis"){
        //     steps{
        //         sh ''' 
        //             echo $SCANNER_HOME
        //             sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner    
        //         '''
        //     }

        //     // steps{
        //     //     sh '''
        //     //         rm sonar-project.properties 
        //     //         sudo $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Amazon -Dsonar.projectKey=Amazon
        //     //     '''
        //     //     // sh '''
        //     //     // rm sonar-project.properties 
        //     //     // sudo $SCANNER_HOME/bin/sonar-scanner 
        //     //     // '''
        //     // }
        // }
    }
}

// sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner