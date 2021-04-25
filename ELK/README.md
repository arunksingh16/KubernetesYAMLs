
# ELK STACK DEPLOYMENT SCENERIOS FOR KUBERNETES

In case if you want to change the default password for OpenDistro in Custom build Docker Image

```
sudo docker run --rm singharunk/elasticsearch:7.10.2-plugin \
/bin/bash -c "export JAVA_HOME=/usr/share/elasticsearch/jdk; export PATH=$PATH:JAVA_HOME=/usr/share/elasticsearch/jdk/bin; \
chmod 775 /usr/share/elasticsearch/plugins/opendistro_security/tools/hash.sh; \
/usr/share/elasticsearch/plugins/opendistro_security/tools/hash.sh -p NewPassword"

```
