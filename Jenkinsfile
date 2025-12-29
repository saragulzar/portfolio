pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    parameters {
        booleanParam(
            name: 'executeTests',
            defaultValue: true,
            description: 'Execute Test Stage'
        )
    }

    environment {
        VERSION = '1.0.0'
    }

    stages {

        stage('Build') {
            steps {
                echo 'Building..'
                echo "Version: ${VERSION}"
                bat 'mvn -version'
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Testing with conditions..'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
