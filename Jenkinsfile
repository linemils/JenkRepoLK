pipeline {
    agent any
    stages {
        stage('install-pip-deps') {
            steps {
                echo 'Installing pip deps...' //izvada tekstu
                powershell 'git clone https://github.com/mtararujs/python-greetings' //klone no repo
                powershell 'ls python-greetings' //skatit mapi
                powershell 'pip install -r python-greetings\\requirements.txt' //instale pip
            }
        }
        stage('deploy-to-dev') {
            steps {
                echo 'Deployment to dev in progress...' //izvada tekstu
                script{
                pm2(7001)
                }
            }
        }
        stage('tests-on-dev') {
            steps {
                echo 'Testing on dev in progress...' //izvada tekstu
                script{
                json_build()
                }
            }
        }
        stage('deploy-to-staging') {
            steps {
                echo 'Deployment to staging in progress..' //izvada tekstu
                script{
                pm2(7002)
                }
            }
        }
        stage('tests-on-staging') {
            steps {
                echo 'Testing on staging in progress...' //izvada tekstu
                script{
                json_build()
                }
            }
        }
        stage('deploy-to-preprod') {
            steps {
                echo 'Deployment to preprod in progress...' //izvada tekstu
                script{
                pm2(7003)
                }
            }
        }
        stage('tests-on-preprod') {
            steps {
                echo 'Testing on preprod in progress...' //izvada tekstu
                script{
                json_build()
                }
            }
        }
        stage('deploy-to-prod') {
            steps {
                echo 'Deployment to prod in progress..' //izvada tekstu
                script{
                pm2(7004)
                }
            }
        }
        stage('tests-on-prod') {
            steps {
                echo 'Testing on prod in progress...' //izvada tekstu
                script{
                json_build()
                }
            }
        }
    }
}

def json_copy(){
powershell 'git clone https://github.com/mtararujs/course-js-api-framework.git'//klone no repo
// nokope json pakotni
powershell 'copy C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-world-pipeline\\course-js-api-framework\\package.json C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\hello-world-pipeline\\ '
powershell 'npm install' //palaizh npm install
}

def pm2(int port){
powershell 'pm2 start python-greetings/app.py --name greetings-app-dev -p ${port}'
powershell 'pm2 delete all'
}
