pipeline {
    agent { label 'linux-node' }
    stages {
        stage('Build') {
            steps {
                script {
                    git (
                        branch: 'main', url: 'https://github.com/rgarlando23/node-webapp.git', credentialsId:'GithubUser' )
                    sh 'cd /home/rgarlando/workspace/node-app'
		    sh 'docker build . -t node-webapp/latest'
                    sh 'docker run -d -p 3000:80 node-webapp/latest'
                }
            }
        }
    }
}
