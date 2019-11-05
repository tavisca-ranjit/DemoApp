pipeline {
    agent any
    parameters{
      string (
        name : 'Environment',
        defaultValue: '',
        description: ''
      )         
     
    }  
    stages {
        stage('Build') {
        when {
            expression { "${params.Environment}" == 'QA' }
          }
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
          when {
            expression { "${params.Environment}" == 'Stage' }
          }
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
         when {
            expression { "${params.Environment}" == 'Prod' }
          }
            steps {
                echo 'Deploying....'
            }
        }
    }
}
