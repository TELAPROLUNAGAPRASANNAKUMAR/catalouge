// #!groovy
// // it means the libraries will be downloaded and accessible at run time
// // @Library('roboshop-shared-library') _

// def configMap = [
//     application: "nodeJSVM",
//     component: "catalogue"
// ]
// env

// // this is .groovy file name and function inside it
// //if not master then trigger pipeline
// if ( ! env.BRANCH_NAME.equalsIgnoreCase('master')){
//     pipelineDecission.decidePipleine(configMap)
// }
// else{
//     echo "master PROD deployment should happen through CR"
// }

pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    // triggers {
    //     cron('* * * * *')
    // }
    environment { 
        USER = 'sivakumar'
    }
    
    stages {

        // stage('Install depdencies') {
        //      steps {
        //          sh 'npm install'
        //     }
        // }
        stage('Unit test') {
             steps {
                 echo "unit testing is done here"
            }
        }
         //sonar-scanner command expect sonar-project.properties should be available
        stage('Sonar Scan') {
             steps {
                 sh 'ls -ltr'
                 sh 'sonar-scanner'
            }
        }
    
        stage('Build') {
            steps {
                echo 'Building..'
              sh '''
                ls -ltr
                pwd
                echo "Hello from GitHub Push webhook event"
                printenv
              '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                //error 'this is failed'
            }
        }
    }

        

      
}