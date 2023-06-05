/*  Name: terra-gcloud-build
    Date: June 4, 2023
    Purpose:  Custom Docker image with Terraform and Gcloud installed.
*/
//
pipeline {
 /*environment {
    PROJECT = "sandbox-io-289003"
    CLUSTER = "jenkins-cd"
    CLUSTER_ZONE = "us-east4-a"
    IMAGE_TAG = "gcr.io/${PROJECT}/${APP_NAME}:${env.BRANCH_NAME}.${env.BUILD_NUMBER}"
    JENKINS_CRED = "${PROJECT}"
    REPO = "smoltzvi/custom-dockerbuild "
  }*/
 agent any /*{
    kubernetes {
      label 'build-deploy-agent'
      defaultContainer 'jnlp'
      yaml """
     apiVersion: v1
kind: Pod
metadata:
labels:
  component: ci
spec:
  # Use service account that can deploy to all namespaces
  serviceAccountName: cd-jenkins
  containers:
   - name: kaniko
     image: gcr.io/kaniko-project/executor:v1.6.0-debug
     imagePullPolicy: Always
     command:
     - sleep
     args:
     - 99d
      """
    }
 }*/
 stages {
    //  Run docker to build image
    stage('Build Docker') {
      steps {
        bat 'docker build -t ubuntu:latest .'
        bat 'docker run -td --name ubuntu_custom ubuntu:latest'
      }
    } 
  }
}  