pipeline {
    agent any 
    tools {
        maven 'Maven'
    }
    stages{
        stage('clone repo'){
            steps{
                git branch: 'master', url: 'https://github.com/Shantanumajan6/project.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('copy file'){
            steps{
                sh 'scp -i /root/LinuxmobaMumbai.pem /root/.jenkins/jobs/job/target/*.war ec2-user@172.31.10.5:/mnt/servers/apache-tomcat-10.1.54/webapps/'
            }
        }
    }
}
