pipeline{
    agent any
    parameters{
        choice(name: 'action', choices: ['build', 'destroy'], description: 'Build Or Destroy Infrastructure')
        sting(name: 'environment', defaultValue: 'default', description: 'Environment name')
        sting(name: 'team', defaultValue: 'default', description: 'Team name')
        sting(name: 'account', defaultValue: 'default', description: 'account name')
        sting(name: 'region', defaultValue: 'us-east-1', description: 'region')
        sting(name: 'cidr', defaultValue: '', description: 'vpc cidr')
        sting(name: 'public_cidr', defaultValue: '', description: 'public cidrs')
        sting(name: 'private_cidr', defaultValue: '', description: 'private cidrs')
        sting(name: 'desired', defaultValue: '', description: 'node group desired')
        sting(name: 'max', defaultValue: '', description: 'node group max capacity')
        sting(name: 'min', defaultValue: '', description: 'node group min capacity')

    }
    stages{
        stage("Init") {
            steps{
                script{
                    sh"ls -l"
                    sh"cat $WORKSPACE/var/terraform/tfvars"
                }
            }

        }
        stage("Build Infrastructure"){
            when { equals expected: 'build', actual: params.action }
            steps{
                script{
                    sh"ls -l"
                }
            }
        }
        stage("Destroy Infrastructure"){
            when { equals expected: 'destroy', actual: params.action }
            steps{
                script{
                    sh"ls -l"
                }
            }
        }
    }
}