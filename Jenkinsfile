pipeline {
    agent any
    stages {
        stage('Checkout') { // добавим новый Stage
            steps {
                git branch: 'main', url: "https://github.com/alekelio/docker_install.git" // используем встроенный в Jenkins плагин Git для скачивания проекта из бранча main
            }
        }
        stage('Deploy') {
            steps {
                sh 'ansible-playbook docker-install.yml -i docker.yml' // поскольку скрипты работают в одной папке, на втором шаге мы можем просто запустить плейбук
            }
        }
    }
}
