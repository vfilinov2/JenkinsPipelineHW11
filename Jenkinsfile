pipeline {
  agent {
    docker {
	image 'vmdocker2022/build_agent:latest'
    }
  }

  stages {

    stage('Clone repo boxfuse') {
      steps {
          git(url: 'https://github.com/vfilinov2/boxfuse.git')
        echo 'Clone repo boxfuse'
      }
    }
	
	stage('Build war') {
      steps {
        sh 'mvn package'
      }
    }
    
    stage('Build prod image') {
      steps {
          // sh 'mkdir prod_image'
          // sh 'cd prod_image'
           git(url: 'https://github.com/vfilinov2/JenkinsPipelineHW11.git')
            //            script {
    //  def dockerImage = docker.build("prod_image", "-f Dockerfile .")
      //docker.withRegistry('', 'dockerhub-creds') {
       // dockerImage.push()
      //  dockerImage.push("latest")
      //          }
      //echo "Pushed Docker Image: ${env.IMAGE_NAME}"
      //      }
     // }
    }
    stage('Run container') {
        steps {
            echo 'Run container'

            //sudo docker pull devcvs-srv01:5000/shop2-backend/gateway-api:2-staging
        }
	}

  }
}

