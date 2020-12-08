```
How to install Jfrog Artifactory...

mkdir -p /jfrog/artifactory
chown -R 1030:1030 /jfrog/artifactory
chown -R 1030:1030 /jfrog/

docker run --name artifactory -d -p 8081:8081 -p 8082:8082 -p 8084:8084 \
  -v /jfrog/artifactory:/var/opt/jfrog/artifactory \
  -e EXTRA_JAVA_OPTIONS='-Xmx4g -Xms512m -Xmx2g -Xss256k -XX:+UseG1GC' \
  docker.bintray.io/jfrog/artifactory-oss:latest
  ```
```
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
```
