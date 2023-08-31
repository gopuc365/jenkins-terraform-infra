pipeline {
    agent any
tools {
"org.jenkinsci.plugins.terraform.TerraformInstallation" "Terraform"
}
parameters {
  string(name: 'WORKSPACE', defaultValue: 'development')
}
environment {
TF_HOME = tool('Terraform')
TP_LOG = "WARN"
PATH = "$TF_HOME:$PATH"
ACCESS_KEY = credentials('AWS_ACCESS_KEY_ID')
SECRET_KEY = credentials('AWS_SECRET_ACCESS_KEY')
}
    stages {
//         stage('Checkout') {
//             steps {
//             checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mydevopscoach/my-tf-iac-aws-repo']]])            

//           }
//         }
        
        stage ("terraform init") {
            steps {
                sh ('terraform init') 
            }
        }
        
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
