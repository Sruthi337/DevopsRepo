pipeline {
    
    agent any

    tools {
        maven "maven_3.8.4"
    }

    stages {
        stage('Build') {
            steps {

                git 'https://github.com/Sruthi337/DevopsRepo.git'

                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                
            }

            post {
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
