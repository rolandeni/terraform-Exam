#!/usr/bin/env groovy
pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION = "us-east-2"
    }
    stages {
        stage("Create an EKS Cluster") {
            steps {
                script {
                    dir('terraform-for-eksxsockshop') {
                        dir('terraform'){
                            sh "terraform init"
                            
                            
        
                        }
                       
                    }
                }
            }
        }
        stage("Deploy to EKS") {
            steps {
                script {
                    dir('terraform-for-eksxsockshop'){
                        dir('kubernetes'){
                            sh "aws eks update-kubeconfig --name myapp-eks-cluster"
                            sh "kubectl apply -f complete-demo.yaml"
                            sh "kubectl get all -n my-sock-shop"
                            sh "kubectl apply -f manifests-monitoring"
                            sh "kubectl apply -f portfolio.yaml"
                            sh "kubectl get deployments,svc"
                        }

                    }
                        
                }
            }
        }
    }
}
