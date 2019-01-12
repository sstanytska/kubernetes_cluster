pipeline{
    agent any
    parameters{
        string(defaultValue: "plan",  name: "action",  description: "Do you want plan/apply/destroy")
    }
    stages{
        stage("Pull repo"){
            steps{
                git 'git@github.com:rameca231190/kubernetes_cluster.git'
            }
        }
        stage("terraform init"){
            steps{
                sh 'cd /var/lib/jenkins/kubernetes_cluster'
                    sh "terraform init"
                }
            }
        stage("terraform plan"){
            steps{
                sh 'cd /var/lib/jenkins/kubernetes_cluster'
                    sh "terraform  ${action} -auto-approve"
                }
            }
        }
    }
