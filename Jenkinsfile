#!/usr/bin/env groovy 
node('jslave1') {
      stage('Repo Pull') {
        echo "${seperator60}\n${seperator20} Checkout Source Repo \n${seperator60}"
        deleteDir()
        checkout scm 
    }
        stage("Test Connection") {
                withCredentials([
                    usernamePassword(credentialsId: 'aws_jenkins',
                    passwordVariable: 'AWS_SECRET_ACCESS_KEY',
                    usernameVariable: 'AWS_ACCESS_KEY_ID'
                )])
                    {
                        sh """
                            aws ec2 describe-instances --region eu-west-2 
                        """
                }     
        }	

}
