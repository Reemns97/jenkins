pipeline {
    agent { docker { image 'bryandollery/terraform-packer-aws-alpine' } }
    options {
        skipStagesAfterUnstable()
    }
    stages {
    stage('CreateDockerFile'){
	    steps {
		sh """echo 'FROM bryandollery/terraform-packer-aws-alpine' > '/Dockerfile'"""
		sh """echo 'RUN echo aa > /Manifest.txt' >> '/Dockerfile'"""   
	}
	}
   stage('BuildDockerfile') {
            steps {
		sh 'docker build --tag reem:\${BUILD_NUMBER /}'
                echo "Done ${cat /Manifest.txt}"
            }
        }
        }
}
