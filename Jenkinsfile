node {
    stage('CheckTerraform') {
        //sh 'cd /var/jenkins_home/workspace/pruebavg '
        script{
            if ( !fileExists ('terraform_0.12.18_linux_amd64.zip' )){
                echo "Check Terraform"
                    sh "apt-get install unzip"
                    sh "wget https://releases.hashicorp.com/terraform/0.12.18/terraform_0.12.18_linux_amd64.zip"
                    sh "unzip terraform_0.12.18_linux_amd64.zip"
                    sh "mv terraform /usr/local/bin/"
            }
        }
        //sh "ls"
        sh  'terraform --version'
        //if ( !fileExists ('main.tf') ) {
               // git branch: 'master', url: 'https://gitlab.digitalcoedevops.com/labs/oe/nodejs-api-oe'
        //}
    }
    stage('Terraform init') {
        echo '\n\nInitializing... \nLooking for *.tf files'
        sh 'terraform init'
    }
    stage('Terraform plan'){
        sh "terraform plan"
    }
    /*stage('Terraform validate'){
        sh "cp /usr/local/bin/terraform /var/jenkins_home/workspace/prueba@tmp/"
        sh "Terraform validate"
    }*/
    stage('Terraform apply'){
        sh "terraform apply"
    }
}
