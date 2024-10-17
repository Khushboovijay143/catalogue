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

        stage('Build') {
            steps {
                sh 'ls -ltr'
                sh 'zip -r catalogue.zip ./* --exclude=.git --exclude=.zip'
            }
        }

    //     post{
    //         always{
    //             echo 'cleaning up workspace'
    //             deleteDir()
    //     }
    // }
    
        post {
        // Clean after build
            always {
                cleanWs(cleanWhenNotBuilt: false,
                        deleteDirs: true,
                        notFailBuild: true,
                        )
        }
    }
    }

}