pipeline {
    agent any
    
    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing pip deps...'
                
                powershell 'git clone https://github.com/mtararujs/python-greetings'

                powershell 'ls python-greetings'

                powershell 'pip install -r python-greetings\\requirements.txt'
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'Deployment to dev in progress...'
                
                powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p 7001'

                powershell 'pm2 delete all'
            }
        }
        stage('tests-on-dev') {
            steps {
                echo 'Testing on dev in progress...'
                
                powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'

                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'

            }
        }
        stage('deploy-to-staging') {
            steps {
                echo 'Deployment to staging in progress..'
                
                powershell 'pm2 start python-greetings/app.py --name greetings-app-staging -p 7002'

                powershell 'pm2 delete all'
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Testing on staging in progress...'
                
                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo 'Deployment to preprod in progress...'
                
                powershell 'pm2 start python-greetings/app.py --name greetings-app-preprod -p 7003'

                powershell 'pm2 delete all'
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo 'Testing on preprod in progress...'
                
                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo 'Deployment to prod in progress..'
                
                powershell 'pm2 start python-greetings/app.py --name greetings-app-prod -p 7004'

                powershell 'pm2 delete all'
            }
        }
        stage('tests-on-prod') {
            steps {
                echo 'Testing on prod in progress...'
                
                powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\pipelineldtest\\ '

                powershell 'npm install'
            }
        }
    }
}
