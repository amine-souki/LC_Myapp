pipeline
{
    agent any
    stages {
        stage ('Pull'){
            steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            credentialsId: 'MyGithub',
                            url: 'https://github.com/amine-souki/LC_Myapp.git']]])
                }
            }
        }
        stage ('Build'){
            steps{
                script{
                    sh "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
                }
            }
        }
    }
}