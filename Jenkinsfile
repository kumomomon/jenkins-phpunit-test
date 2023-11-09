pipeline {
	agent {
		docker {
			image 'composer:latest'
		}
	}
	stages {
		stage('Checkout SCM') {
			steps {
				git 'https://github.com/simyucheng/jenkins-phpunit-test.git'
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