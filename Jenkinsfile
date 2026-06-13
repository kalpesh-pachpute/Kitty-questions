pipeline {
agent any

```
environment {
    APP_NAME = "kitty-app"
}

stages {

    stage('Checkout Code') {
        steps {
            git branch: 'main',
            url: 'https://github.com/USERNAME/REPOSITORY.git'
        }
    }

    stage('Verify Docker') {
        steps {
            sh 'docker --version'
            sh 'docker compose version'
        }
    }

    stage('Build Containers') {
        steps {
            sh 'docker compose build'
        }
    }

    stage('Deploy Containers') {
        steps {
            sh 'docker compose down'
            sh 'docker compose up -d'
        }
    }

    stage('Verify Deployment') {
        steps {
            sh 'docker ps'
        }
    }
}

post {
    success {
        echo 'Deployment Successful'
    }

    failure {
        echo 'Deployment Failed'
    }
}
```

}
