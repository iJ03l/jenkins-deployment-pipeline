#!/usr/bin/env groovy
pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION = "us-east-1"
    }
    // stages {
    //     stage("Create an EKS Cluster") {
    //         steps {
    //             script {
    //                 dir('terraform') {
    //                     sh "terraform init"
    //                     sh "terraform apply -auto-approve"
    //                 }
    //             }
    //         }
    //     }
    //     stage("Deploy to EKS") {
    //         steps {
    //             script {
    //                 dir('kubernetes') {
    //                     sh "aws eks update-kubeconfig --name myapp-eks-cluster"
    //                     sh "kubectl apply -f nginx-deployment.yaml"
    //                     sh "kubectl apply -f nginx-service.yaml"
    //                     sh "kubectl create namespace sock-shop"
    //                     sh "kubectl apply -f sock-shop.yaml"
    //                 }
    //             }
    //         }
    //     }
    stages("Get EKS Nodes") {
        steps {
            script {
                dir('kubernetes') {
                    sh "kubectl get nodes -o wide"
                    sh "kubectl get svc"
                }
            }
        }
    }
    }
}