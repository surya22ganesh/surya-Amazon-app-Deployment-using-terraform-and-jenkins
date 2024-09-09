pipeline {
    agent any
    environment {
        SCANNER_HOME='/opt/sonarscanner/sonarscanner'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'ls'
            }
        }
        // stage('rm sonar-project.properties file'){
        //     steps{
        //         sh 'rm sonar-project.properties'
        //     }
        // }
        // stage("Sonarqube analysis"){
        //     steps{
        //         sh 'sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner -Dsonar.projectKey=demo -Dsonar.sources=. -Dsonar.host.url=http://3.145.217.31:9000 -Dsonar.token=sqp_b5e3a7ad93a37b439b18a89beaadc3fda58a7307'
        //     }
        // }
        //  stage("quality gate"){
        //    steps {
        //         script {
        //             waitForQualityGate abortPipeline: false, credentialsId: 'jenkins' 
        //         }
        //     } 
        // }
        stage('Install Dependencies') {
            steps {
                sh "npm install"
            }
        }

    }
}

// sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner