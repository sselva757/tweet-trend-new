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
}

