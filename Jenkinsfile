pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                //sh 'make'
                //archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                /* `make check` returns non-zero on test failures,
                * using `true` to allow the Pipeline to continue nonetheless
                */
                sh 'make check || true' 
                junit '**/target/*.xml' 
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
