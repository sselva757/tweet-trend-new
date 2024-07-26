pipeline {
    agent {
        node {
            label 'maven-slave-machine'
        }
    }

    stages {
        stage('build') {
            steps {
	    sh 'mvn clean deploy'
            }
        }
    }
}

