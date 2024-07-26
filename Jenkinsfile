pipeline {
    agent {
        node {
            label 'maven-slave-machine'
        }
    }

    stages {
        stage('build') {
            steps {
                git branch: 'main', url: 'https://github.com/ravdy/tweet-trend-new.git'
            }
        }
    }
}

