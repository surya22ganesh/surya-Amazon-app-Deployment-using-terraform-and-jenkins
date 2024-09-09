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
        stage('rm sonar-project.properties file'){
            steps{
                sh 'rm sonar-project.properties'
            }
        }
        stage("Sonarqube analysis"){
            steps{
                sh ''' 
                    echo $SCANNER_HOME
                    sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner -Dsonar.projectKey=Amazon -Dsonar.sources=. -Dsonar.host.url=http://3.15.166.118:9000 -Dsonar.token=sqp_aea4af6a3e97ed18c79f1dc3b5c8bcbaaf9ee73b   
                '''
            }

            // steps{
            //     sh '''
            //         rm sonar-project.properties 
            //         sudo $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=Amazon -Dsonar.projectKey=Amazon
            //     '''
            //     // sh '''
            //     // rm sonar-project.properties 
            //     // sudo $SCANNER_HOME/bin/sonar-scanner 
            //     // '''
            // }
        }
    }
}

// sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner