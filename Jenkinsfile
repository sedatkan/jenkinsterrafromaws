pipeline {
 
  agent {
    docker {
      image 'hashicorp/terraform:light'
      args '--entrypoint='
    }
  }
  stages {
    stage('Terraform Plan') { 
      steps {
        
        sh 'echo started'  
        sh  'terraform init'
        sh  'terrafrom validate'
        sh 'terraform plan -no-color -out=create.tfplan' 
      }
    }
  
    stage ('Terraform Apply') {
      steps{
      sh "terraform validate"
      }
          
      }
  }
}
