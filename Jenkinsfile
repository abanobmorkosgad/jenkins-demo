pipeline {
     agent any
    parameters {
        booleanParam(name:'project', defaultValue: true, description:'this paramater help you to know project name')
        choice(name: 'namespace', choices:['dev','prod','stage'], description: '' ) 
    }


    environment {
        lab_number = "2"
    }

    stages {
        stage('check') {
            steps {
                echo "checking your code"
                
               
            }
        }

        stage('test') {
            when {
                expression{
                    params.project == false
                }
            }
            steps {
                echo "testing your app" 
            }
        }
        
        stage('deployment') {  
            steps {
                echo "kubectl apply -f deployment.yaml $params.namespace"
                echo "your code is deployed right now"
                echo "this build number $BUILD_NUMBER"
                echo "this lab ${lab_number}"
            }
        }    
    }

}
