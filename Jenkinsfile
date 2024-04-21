pipeline{
	
	 agent { 
                label 'linux'
            }
	

 environment {
        WEBSITE_SERVER="/server/entry.express.js"
        PM2_ECOSYSTEM_CONFIGS_US = "ecosystem.config.cjs"
        PM2_ECOSYSTEM_CONFIGS_UK = "ecosystem.config.cjs"
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
        WEBSITE_FOLDERS_US="www.printerpix.com"
        WEBSITE_FOLDERS_UK="www.printerpix.co.uk"
        WEBSITE_FOLDERS_DE="www.printerpix.de"
        WEBSITE_FOLDERS_ES="www.printerpix.es"
        WEBSITE_FOLDERS_FR="www.printerpix.fr"
        WEBSITE_FOLDERS_IT="www.printerpix.it"
        WEBSITE_FOLDERS_NL="www.printerpix.nl"
        WEBSITE_APP_US = "$WEBSITE_FOLDERS_US$WEBSITE_SERVER"
        WEBSITE_APP_UK = "$WEBSITE_FOLDERS_UK$WEBSITE_SERVER"
        WEBSITE_APP_DE = "$WEBSITE_FOLDERS_DE$WEBSITE_SERVER"
        WEBSITE_APP_ES = "$WEBSITE_FOLDERS_ES$WEBSITE_SERVER"
        WEBSITE_APP_FR = "$WEBSITE_FOLDERS_FR$WEBSITE_SERVER"
        WEBSITE_APP_IT = "$WEBSITE_FOLDERS_IT$WEBSITE_SERVER"
        WEBSITE_APP_NL = "$WEBSITE_FOLDERS_NL$WEBSITE_SERVER"
        WORKSPACE = "${env.WORKSPACE}"
        TOKEN = credentials('telegram-token')
        CHAT_ID = credentials('telegram-chatid')
    //     branch = 'main'
    //     scmUrl = 'https://github.com/salmanspice/SimpleNodeJSAppForJenkins.git'
              }
		
	stages{

		stage("Pipeline Details"){
			steps{
				sh """
             echo "The current branch name  is ${env.BRANCH_NAME}"
             echo "The current Build number  is ${env.BUILD_NUMBER}"
             echo "The current Job Name   is ${env.JOB_NAME}"
             echo "The current Workspace  is ${env.WORKSPACE}"
             echo "The current git branch  is ${env.GIT_BRANCH}"
             echo "The current git URL  is ${env.GIT_URL}"
	     """ 
        
			}
		}
		stage("Using env vars"){
			 agent { 
                label 'linux'
            }
			steps{
				sh """
				#echo "BUILD_NUMBER = ${env.BUILD_NUMBER}"
                 #echo "BUILD_NUMBER = $BUILD_NUMBER"
                  #echo "WEBSITE_PORTS_US =${env. WEBSITE_PORTS_US}"
				  #echo "SERVER_${env. WEBSITE_PORTS_US}"
                                   #echo "SERVER_${env. WEBSITE_PORTS_UK}"
				   #echo "SERVER_${env. WEBSITE_PORTS_FR}"
                   echo "${env.WEBSITE_APP_US}"
				  cd /pipeline 
                        #sed -i -E 's/name: "www.printerpix.com"/name: "${env.WEBSITE_FOLDERS_UK}"/' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"    #best
	                       
			 sed -i -E 's/script: "/var/www/www.printerpix.com${env.WEBSITE_SERVER}"/script: "${env.WEBSITE_APP_UK}\"/' "${env.PM2_ECOSYSTEM_CONFIGS_UK}" 
                         #sed -i -E 's/"PORT":  "3000"/"PORT":  "${env.WEBSITE_PORTS_UK}\"/' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"#best


      
                                 #sed -i -E 's/(.*PORT.*:).*/ \"${env.WEBSITE_PORTS_UK}\",/g' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
				 #sed -i -E 's/(.*PORT.*:).*/\1 \"${env.WEBSITE_PORTS_UK}\",/g' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
                                  #sed  -i -E 's/(.*PORT.*:).*/\1 \"${env.WEBSITE_PORTS_UK}\",/g' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
				  #sed -i -E 's/(.*PORT=.*:).*/\1  \"${env.WEBSITE_PORTS_UK}\",/g' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
                               #sed -i -E 's/"name": "www.printerpix.com"/"name":  "${env.WEBSITE_FOLDERS_UK}\"/' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
			        #sed -i -E 's/name: "www.printerpix.com"/name: "${env.WEBSITE_FOLDERS_UK}"/' "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
				  #awk '/"PORT": "3000"/ {gsub("3000", "${env.WEBSITE_PORTS_UK}")} 1' "${env.PM2_ECOSYSTEM_CONFIGS_UK}" > "${env.PM2_ECOSYSTEM_CONFIGS_UK}".tmp && mv "${env.PM2_ECOSYSTEM_CONFIGS_UK}".tmp "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
                   #awk '/"name": "www.printerpix.com",/ {gsub("www.printerpix.com", "${env.WEBSITE_FOLDERS_UK}")} 1' "${env.PM2_ECOSYSTEM_CONFIGS_UK}" > "${env.PM2_ECOSYSTEM_CONFIGS_UK}".tmp && mv "${env.PM2_ECOSYSTEM_CONFIGS_UK}".tmp "${env.PM2_ECOSYSTEM_CONFIGS_UK}"
		   
     #awk -F ',' -v new="${env.WEBSITE_FOLDERS_UK}" '/"name": "www.printerpix.com"/ {gsub("www.printerpix.com", new)} 1' "${env.PM2_ECOSYSTEM_CONFIGS_UK}" > "${env.PM2_ECOSYSTEM_CONFIGS_UK}.tmp" && mv "${env.PM2_ECOSYSTEM_CONFIGS_UK}.tmp" "${env.PM2_ECOSYSTEM_CONFIGS_UK}"

				  
	              """

			}
		}
	}


}
