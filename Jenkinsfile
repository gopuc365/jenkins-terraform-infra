pipeline {
    agent any

    stages {
//         stage('Checkout') {
//             steps {{withAWS(credentials: 'jenkinsdemo')
//             checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/mydevopscoach/my-tf-iac-aws-repo']]])            

//           }
//         }
    }
        stage ("terraform init") {
            steps {withAWS(credentials: 'jenkinsdemo')
                sh ('terraform init') 
            }
        }
    }
        stage ("terraform Action") {
            steps {{withAWS(credentials: 'jenkinsdemo')
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
}
