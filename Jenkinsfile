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
        stage('kubernetes-deploy'){
            steps {
                sh 'az login --service-principal -u 5ab85e42-081b-4ced-8259-68a3639cb69d -p c-v8Q~LqY1c7KbVZtahmi3nwNcyxsikys-WBIa9i -t bec72b1b-ba20-4d6c-ac90-18faac0e5126'
                sh 'az aks command invoke --resource-group rg-poclot-dev-gwc-aks --name aks-poclot-dev-gwc-lotto --command "kubectl rollout restart deployment/gms-deployment -n md1"'
            }
        }
    }
}



