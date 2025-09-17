pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/dugutarithish/Jenkins-CI-CD-for-a-Python-App'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-python-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 my-python-app'
            }
        }
    }
}
