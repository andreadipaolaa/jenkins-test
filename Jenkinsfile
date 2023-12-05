pipeline {
    agent any
    environment {
        DOCKER_REGISTRY = 'acrpoclotdevlotto.azurecr.io'
        PROJECT_PATH = '/var/jenkins_home/workspace/esting_testing_MAVEN_build_trunk'
    }

    stages {
        stage('docker-build'){
            steps {
                sh 'docker build -t ${DOCKER_REGISTRY}/gms ${PROJECT_PATH}/DGP_GameManagementSystem/'
            }
        }
        stage('docker-push'){
            steps {
                sh 'docker login -u acrpoclotdevlotto -p TVmsgWdtCDOra0m+kmbtmriyJ43mYbxPK/Ab3P00XO+ACRA1Ms0g ${DOCKER_REGISTRY}'
                sh 'docker push ${DOCKER_REGISTRY}/gms'
            }
        }
    }
}



