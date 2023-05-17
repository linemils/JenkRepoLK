pipeline {
    agent any

    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing pip dependencies...'
                // Clone the repository
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                // Check for the existence of required files if necessary
                powershell 'ls python-greetings\\required_files'

                // Install the necessary libraries
                powershell 'pip install -r python-greetings\\requirements.txt'
                
                echo 'Hello World'
            }
        }
      stage('deploy-to-dev') {
            steps {
                echo 'Deploying to dev...'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dep-dev -p 7001'
                powershell 'pm2 delete all'
            }
        }
      stage('tests-on-dev') {
            steps {
                echo 'Testing on dev'
                powershell 'pm2 start python-greetings/app.py --name greetings-app-test-dev -p 7001'
                powershell 'pm2 delete all'
            }
        }
      stage('deploy-to-staging') {
            steps {
                echo 'Deploying to staging'
            }
        }
      stage('tests-on-preprod') {
            steps {
                echo 'Testing on prepod'
            }
        }
      stage('deploy-to-prod') {
            steps {
                echo 'Deploying to prod'
            }
        }
      stage('tests-on-prod') {
            steps {
                echo 'Testing on prod'
            }
        }
    }
}
