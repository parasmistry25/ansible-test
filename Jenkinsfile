pipeline
{
    agent {
        label 'ansible'
    }
     stages {
        stage("Checkout") {
      	steps {
          checkout([$class: 'GitSCM',
          branches: [[name: '*/master']],
          extensions: [],
          userRemoteConfigs: [[url: 'https://github.com/parasmistry25/ansible-test.git']]])
            }
        }
        stage("check current direct") {
            steps {
                sh  '''hostname ; pwd 
                 ${WORKSPACE}'''
            }
        }
        stage("ansible check connection") {
            steps {
                sh  ''' ansible-playbook nginx.yaml -t deployment'''
            }
        }      

    }



}