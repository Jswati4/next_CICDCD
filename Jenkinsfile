pipeline {
    agent {
        label "${AGENT}"
    }

    stages {
        stage('Continuous Integration') {
            steps {
                git branch: 'main', url: 'https://github.com/Jswati4/next_CICDCD'
            }
        }

        stage('Continuous Delivery') {
            steps {
                sh 'docker build . -t ${DOCKERHUB_USERNAME}/next_CICDCD'
                sh 'docker login -u ${DOCKERHUB_USERNAME} -p ${DOCKERHUB_PASSWORD}'
                sh 'docker push ${DOCKERHUB_USERNAME}/next_CICDCD'
            }
        }
    }
}