pipeline {
    agent any
    environment {
        SCANNER_HOME='/opt/sonarscanner/sonarscanner'
    }

    stages {
        stage('Hello') {
            steps {
                echo 'pipeline started'
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

        // stage('Install Dependencies') {
        //     steps {
        //         sh "npm install"
        //     }
        // }
        // stage('trivy fs scan'){
        //     steps{
        //         sh 'trivy fs . > trivyfs.txt'
        //     }
        // }
        stage('docker build'){
            steps{
                sh 'sudo docker build -t surya22ganesh/amazonclone .'
            }
        }
        stage('trivy image scan'){
            steps{
                sh 'sudo trivy image surya22ganesh/amazonclone:latest > trivyimage.txt'
            }
        }
        stage('docker container run') {
            steps {
                script {
                    try {
                        echo 'Starting Docker conatiner...'
                        sh 'sudo docker run -dit --name amazonclonecontainer -p 3000:3000 surya22ganesh/amazonclone'
                    } catch (Exception e) {
                        echo 'catched the error ! Error: ' + e.toString()
                        sh 'sudo docker rm amazonclonecontainer -f'
                        currentBuild.result = 'FAILURE'
                    } finally {
                        echo 'Cleaning up...'
                        sh 'sudo docker run -dit --name amazonclonecontainer -p 3000:3000 surya22ganesh/amazonclone'
                    }
                }
            }
        
        }
        stage('docker hub push'){
            steps{
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://hub.docker.com/') {
                    // some block
                    sh '''
                        sudo docker push surya22ganesh/amazonclone
                    '''
                }
            }
        }
        stage('ended'){
            steps{
                sh 'pipeline ended.'
            }
        }   

    }
}

// sudo sh /opt/sonarscanner/sonarscanner/bin/sonar-scanner

// cloudbees dockerregistry plugin