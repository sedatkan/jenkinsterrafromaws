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
        sh  'terraform validate'
        sh  'terraform plan -no-color -out=create.tfplan' 
        sh  'terrafrom apply'
        input ('Execute plan')        
}
    }
  
    stage ('Terraform Apply') {
      steps{
      sh "terraform validate"
      }
          
      }
  }
}
