pipeline {
	agent  {
		docker {
			// image 'composer:latest'
			image 'composer:latest'
            		args '-v /var/run/docker.sock:/var/run/docker.sock' // This line mounts the Docker socket inside the container
		}
	}
	stages {
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
