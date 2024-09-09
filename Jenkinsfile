pipeline {
    agent any
    environment {
        SCANNER_HOME='/opt/sonarscanner/sonarscanner'
    }

    stages {
        stage('clean workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
                sh 'ls'
            }
        }
        stage('rm sonar-project.properties file'){
            steps{
                sh 'rm sonar-project.properties'
            }
        }
        stage("Sonarqube analysis"){
            steps{
                sh '
                    sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner -Dsonar.projectKey=demo -Dsonar.sources=. -Dsonar.host.url=http://3.142.187.101:9000 -Dsonar.token=sqp_6003ab206a25b34d26951e96866ada0a9ba6364a   
                '
            }
        }
        //  stage("quality gate"){
        //    steps {
        //         script {
        //             waitForQualityGate abortPipeline: false, credentialsId: 'jenkins' 
        //         }
        //     } 
        // }
        // stage('Install Dependencies') {
        //     steps {
        //         sh "npm install"
        //     }
        // }

    }
}

// sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner