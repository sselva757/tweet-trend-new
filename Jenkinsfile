pipeline {
    agent {
        node {
            label 'maven-slave-machine'
        }
    }
environment {
  PATH = "/opt/apache-maven-3.9.8/bin:$PATH"
}
    stages {
        stage('build') {
            steps {
	    sh 'mvn clean deploy'
            }
        }
    }
    stage('SonarQube analysis') {
    environment {
     scannerHome = tool 'sonarscanner'
    }
    steps {
    withSonarQubeEnv('sonar-server-cloud') { // If you have configured more than one global server connection, you can specify its name
      sh "${scannerHome}/bin/sonar-scanner"
    }
    }
  }
}

