pipeline {
    agent { node { label 'Agent' } }

    stages {

        stage('Install depdencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Unit test') {
            steps {
                echo "unit testing is done here"
            }
        }
        //sonar-scanner command expect sonar-project.properties should be available
        stage('Sonar Scan') {
            steps {
                sh 'sonar-scanner'
                echo "Sonar scan done"
            }
        }
    }

}