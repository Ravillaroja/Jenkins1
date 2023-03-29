node{
    stage('git-checkout'){
        git credentialsId: 'github', url: 'https://github.com/Ravillaroja/DevOpsClassCodes.git'
    }
    stage('maven-install'){
        sh 'mvn clean install'
    }
    stage('docker-image'){
        sh 'docker build -t dockerfile /var/lib/jenkins/workspace/NewTask/target
    }
    stage('docker-login'){
        withCredentials([string(credentialsId: 'doc-cred', variable: 'rr'), string(credentialsId: 'doc-cred', variable: '')]) {
    }
    }
    stage('docker-push'){
        sh 'docker push ravillaroja/dockerfile:latest'
    }
    stage('docker-pull'){
        sh 'docker pull ravillaroja/dockerfile:latest'
    }
    stage ('docker Run'){
        sh 'docker run -itd --name junnu -p 8088:8080 ravillaroja/dockerfile:latest'
    }
}
