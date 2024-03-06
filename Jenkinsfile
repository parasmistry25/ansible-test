pipeline
{
    agent {
        label 'ansible'
    }
    stages {
        stage("Checkout Ansible Code") {
      	  steps {
          checkout([$class: 'GitSCM',
          branches: [[name: '*/master']],
          extensions: [],
          userRemoteConfigs: [[url: 'https://github.com/parasmistry25/ansible-test.git']]])
            }
        }
         stage("ansible play for download nginx") {
            steps {
                sh  ''' ansible-playbook pre_tasks.yaml '''
            }
        }      

        stage("ansible check connection") {
            steps {
                sh  ''' ansible-playbook ${type}.yaml -e jenkinsdir=${WORKSPACE} -t ${mode} '''
            }
        }      
  }

}



