pipeline {
    agent any
    stages {
        stage (git) {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/pet_shop.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
               deploy adapters: [tomcat9(path: '', url: 'http://52.195.177.242:8081/')], contextPath: 'charan', war: '**/*.war'
            }
        }
    }
}
