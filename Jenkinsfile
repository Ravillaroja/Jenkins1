pipeline {
    agent any
    stages {
        steps ('Build') {
        steps{
            sh 'printenv'
        }
    }
    stgae ('publish ECR') {
        steps {
            withEnv (["AWS_ACCESS_KEY_ID-${env.AWS_ACCESS_KEY_ID)", "AWS_SECRET_ACCESS_KEY-$(env.AWS_SECRET_ACCESS_KEY)","AWS_DEFAULT_REGION-$(env.AWS_DEFAULT_REGION}"]) {
                sh 'docker login -u AWS -p $(aws ecr-public get-login-password --region us-east-1) public.ecr.aws/x9r9s8o0'
                sh 'docker build -t ecr-demoing'
                sh 'docker tag ecr-demoing ""$BUILD_ID""'
                sh 'docker push public.ecr.aws/x9r9s8o0/ecr-demoing:$""BUILD_ID"
            }
           }
          }
        }
      
                      
                      
