pipeline {
    agent any

    options {
        timestamps()
    }

    stages {

        stage('Compile') {
            steps {
                withMaven(maven: 'MAVEN_HOME') {
                    sh 'mvn -f /Users/jo/.jenkins/workspace/DeclarativePipelineDemo/Demo/pom.xml clean install' //filepath
                }
            }
        }
}
