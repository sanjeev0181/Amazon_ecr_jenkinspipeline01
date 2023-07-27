pipeline {
    agent any 
        environment {
            AWS_ACCOUNT_ID="243250302162"
            AWS_DEFAULT_REGION="us-east-1" 
            IMAGE_REPO_NAME="aecr_jenkinspipeline01"  //ecr repo name
            IMAGE_TAG=    "${env.BUILD_NUMBER}"
            REPOSITORY_URI = "${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}"   
            //                 243250302162   .dkr.ecr.    us-east-1.amazonaws.com/
        } 
        stages {
            stage("Logging into AWS ECR") {
                steps {
                  sh "aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 243250302162.dkr.ecr.us-east-1.amazonaws.com"
                }
            }
        //     stage("Build the docker image"){
        //         steps {
        //             sh "docker build -t ${IMAGE_REPO_NAME} ."
        //         }
        //     }
        //     stage("Pushing to ECR") {
        //         steps {

        //             sh "docker tag ${IMAGE_REPO_NAME}:${IMAGE_TAG} ${REPOSITORY_URI}:$IMAGE_TAG"
        //             sh "docker push ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}:${IMAGE_TAG}"
        //             sh "docker run -d -p 80:80  ${AWS_ACCOUNT_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com/${IMAGE_REPO_NAME}:${IMAGE_TAG}"
        //         }
        //     }
        // }
    }
}

