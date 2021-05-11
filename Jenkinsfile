pipeline {
    
    environment {
        PROD_IMAGE      = 'vmdocker2022/prod_image'
        CONTAINER_NAME   = 'hello10'
    }
    agent {
        docker {
                    image 'vmdocker2022/build_agent'
                    registryCredentialsId '3710df14-95d1-4344-8093-369064d57833'
                    args '-v /var/run/docker.sock:/var/run/docker.sock:rw,z'
                
            }
    }

    stages {
        stage('Clone boxfuse') {
            steps {
                    git(url: 'https://github.com/vfilinov2/boxfuse.git')
            }
        }
        stage('Build war') {
            steps {
                    sh 'docker stop ${CONTAINER_NAME}'
                    sh 'docker rm -f ${CONTAINER_NAME}'
                    sh 'mvn package'
            }
        }
        stage('Clone prod Dockerfile') {
            steps {
                   git(url: 'https://github.com/vfilinov2/JenkinsPipelineHW11.git')
            }
        }    
        stage('Build and push prod image') {    
            steps {
                    script {
                            def dockerImage = docker.build("${PROD_IMAGE}", "-f ./prod/Dockerfile .")
                            docker.withRegistry('', '3710df14-95d1-4344-8093-369064d57833') {
                                  dockerImage.push("latest")
                                }
                            }
            }
        }
        stage('Run container') { 
            steps {
                   sh 'docker run -i -d -t -p 80:8080 --name=${CONTAINER_NAME} ${PROD_IMAGE}'
            }
        } 
    }
}
