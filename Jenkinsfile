pipeline{
    agent{
        label 'linux'
    }
    stages{
        stage('git'){
            steps{
                git branch: 'main', credentialsId: '699ff1ff-7cdf-4c62-b241-4875d7c6982a', url: 'https://github.com/keeper521/ELK.git'
            }
        }
        stage('install'){
            steps{
                sh 'cd /opt/jenkins_agent/workspace/Freestyle-job/roles/kibana && pip3 install -r test-requirements.txt'
            }
        }
        stage('run molecule'){
            steps{
                sh 'cd /opt/jenkins_agent/workspace/Freestyle-job/roles/kibana && molecule test'
            }
        }
    }
}
