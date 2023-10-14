pipeline{
	agent any 
	stages{
		stage('clonecode'){
			steps{
				checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'team7-git-id', url: 'https://github.com/Kondji237/Project4Group6.git']])
				}
			}
            stage('1st parallel'){
			parallel{
			stage('Divine'){
                when {
                    branch 'main'
                }
				steps{
					sh 'uname -a'
					sh 'lscpu'
				}
			}
			stage('Ngantcha'){
                when {
                    branch 'develop'
                }
				steps{
					sh 'df -h'
					sh 'free -g'
				}
			}
			}
			}
			stage('2nd parallel'){
			parallel{
			stage('Steeve'){
                when {
                    branch 'main'
                }
				steps{
					sh 'lsblk'
					sh 'uptime'
				}
			}
			stage('Ngaleu'){
                when {
                    branch 'develop'
                }
				steps{
					sh 'cal'
					sh 'sudo systemctl status jenkins'
				}
			}
			}
            } 
	}
}