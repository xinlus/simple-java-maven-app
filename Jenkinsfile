pipeline {
    agent any

    stages {
        stage('pull code') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master'], [name: '*/dev']], extensions: [], userRemoteConfigs: [[credentialsId: '92f8fceb-e17e-4e8b-aa7e-fb96e78eab5c', url: 'git@github.com:xinlus/simple-java-maven-app.git']]])
            }
        }
        stage('build project') {
            steps {
                  sh 'mvn clean -Dmaven.test.skip=true package'  
                }
        }
    }
}
