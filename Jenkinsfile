pipeline {
    agent any
    environment {
        DOCKER_REGISTRY = 'acrpoclotdevlotto.azurecr.io'
        PROJECT_PATH = '/var/jenkins_home/workspace/testing_testing_dgp_cloud_trunk'
    }

    stages {
        stage('docker-build'){
            steps {
                sh 'docker build -t ${DOCKER_REGISTRY}/gts ${PROJECT_PATH}/DGP_GameManagementSystem/'
            }
        }
    }
}



