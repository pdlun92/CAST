pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'ssh plundgr@c650f03p41-ug "/u/plundgr/CI/build.sh"'
                sh 'ssh root@c650mnp02-ug "/u/plundgr/CI/install.sh"'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'ssh root@c650mnp02-ug "/test/results/clean_logs.sh"'
                sh 'ssh root@c650mnp02-ug "/u/plundgr/CAST/csmtest/tools/complete_fvt.sh"'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
