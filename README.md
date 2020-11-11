==========================================================================================
Jfrog api-key - AKCp8hz3VmBKQkdSAtcjWKKPVCJaN4rXpusWxCLwKRgGRzxr7LLNjfxY3KnCdUMpBxTEUSY3X
==========================================================================================
#########################################################################################
Upload to JFrog Artifactory through Credentials
===============================================
curl -sSf -u "admin:password123" \
       -X PUT \
       -T cloudendure.log \
       'http://192.168.9.5:8081/artifactory/libs-release/'

#########################################################################################
#########################################################################################
upload to JFrog Artifactory through Api Token
---------------------------------------------
curl -sSf -H "X-JFrog-Art-Api:AKCp8hz3VmBKQkdSAtcjWKKPVCJaN4rXpusWxCLwKRgGRzxr7LLNjfxY3KnCdUMpBxTEUSY3X" \
       -X PUT \
       -T anaconda-ks.cfg \
       'http://192.168.9.5:8081/artifactory/libs-release/'
#########################################################################################
#########################################################################################
Download from JFrog Artifactory Through api-token
-------------------------------
curl -u admin:AKCp8hz3VmBKQkdSAtcjWKKPVCJaN4rXpusWxCLwKRgGRzxr7LLNjfxY3KnCdUMpBxTEUSY3X http://192.168.9.5:8081/artifactory/libs-release/cloudendure.log -o /tmp/cloudendure.log
#########################################################################################
#########################################################################################
Download from JFrog Artifactory Through credentials
curl -u admin:password123 http://192.168.9.5:8081/artifactory/libs-release/cloudendure.log -o /tmp/cloudendure.log
#########################################################################################
