pipeline {
    agent {
        node {
            label 'my-slave'
        }
    }
environment {
  PATH = "/usr/share/maven/bin:$PATH"
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

