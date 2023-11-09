pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
    options {
        skipDefaultCheckout true
    }
    stages {
        stage('Checkout') {
            steps {
                script {
                    git branch: 'master', url: 'https://github.com/your-username/your-repository.git'
                }
            }
        }
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit tests'
            }
		}
	}
}
