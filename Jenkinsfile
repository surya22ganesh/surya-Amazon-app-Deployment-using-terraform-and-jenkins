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
                    sudo mvn sonar:sonar -Dsonar.url=http://localhost:9000/ -Dsonar.login=squ_54d0d96f2cbe93f13e354de74934aef477c86514 
                    -Dsonar.projectName=amazon-clone -Dsonar.java.binaries=. -Dsonar.projectKey=amazon-clone
                '''
            }
        }
    }
}
