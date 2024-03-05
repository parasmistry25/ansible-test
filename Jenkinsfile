pipeline
{
    agent {
        label 'ansible'
    }
    
    stage("Checkout Ansible Code") {
      	steps {
          checkout([$class: 'GitSCM',
          branches: [[name: '*/master']],
          extensions: [],
          userRemoteConfigs: [[url: 'https://github.com/parasmistry25/ansible-test.git']]])
        }
    }
       
        // stage("ansible check connection") {
        //     steps {
        //         sh  ''' ansible-playbook nginx.yaml -e jenkinsdir=${WORKSPACE} -t ${mode}'''
        //     }
        // }      

}



