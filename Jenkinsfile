pipeline{
	 agent { 
                label 'linux'
            }

 environment {
        PM2_ECOSYSTEM_CONFIGS_US = "ecosystem.config.cjs"
        PM2_ECOSYSTEM_CONFIGS_UK = "ecosystem.config.js"
        PM2_ECOSYSTEM_CONFIGS_DE = "ecosystem.config.js"
        PM2_ECOSYSTEM_CONFIGS_ES = "ecosystem.config.js"
        PM2_ECOSYSTEM_CONFIGS_FR = "ecosystem.config.cjs"
        PM2_ECOSYSTEM_CONFIGS_IT = "ecosystem.config.cjs"
        PM2_ECOSYSTEM_CONFIGS_NL = "ecosystem.config.js"
        WEBSITE_PORTS_US = "3000"
        WEBSITE_PORTS_UK = "3001"
        WEBSITE_PORTS_DE = "3002"
        WEBSITE_PORTS_ES = "3003"
        WEBSITE_PORTS_FR = "3004"
        WEBSITE_PORTS_IT = "3005"
        WEBSITE_PORTS_NL = "3006"
        WORKSPACE = "${env.WORKSPACE}"
        TOKEN = credentials('telegram-token')
        CHAT_ID = credentials('telegram-chatid')
    //     branch = 'main'
    //     scmUrl = 'https://github.com/salmanspice/SimpleNodeJSAppForJenkins.git'
              }
	stages{
		stage("List env vars"){
			steps{
				sh "printenv | sort"
			}
		}
		stage("Using env vars"){
			 agent { 
                label 'linux'
            }
			steps{
				sh """
				echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"
                 echo "BUILD_NUMBER = $BUILD_NUMBER"
                  echo "WEBSITE_PORTS_US =${env. WEBSITE_PORTS_US}"
				  echo "SERVER_${env. WEBSITE_PORTS_US}"
                                   echo "SERVER_${env. WEBSITE_PORTS_UK}"
				   echo "SERVER_${env. WEBSITE_PORTS_FR}"
				  cd /pipeline
                                 sed -i -E 's/(.*PORT.*:).*/\1 \${env.WEBSITE_PORT_UK},/g' ${env.PM2_ECOSYSTEM_CONFIGS_US}
				  
	              """

			}
		}
	}

}
