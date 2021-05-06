
# ELK STACK DEPLOYMENT SCENERIOS FOR KUBERNETES

In case if you want to change the default password for OpenDistro in Custom build Docker Image

```
sudo docker run --rm singharunk/elasticsearch:7.10.2-plugin \
/bin/bash -c "export JAVA_HOME=/usr/share/elasticsearch/jdk; export PATH=$PATH:JAVA_HOME=/usr/share/elasticsearch/jdk/bin; \
chmod 775 /usr/share/elasticsearch/plugins/opendistro_security/tools/hash.sh; \
/usr/share/elasticsearch/plugins/opendistro_security/tools/hash.sh -p NewPassword"

```


# In case you want to handle certs in OpenDistro 

```
# cert
openssl pkcs12 -in certs_pack.pfx -clcerts -nokeys -out elastic-certificate.crt

openssl x509 -in elastic-certificate.crt -out elastic-certificate.pem -outform PEM

# key
openssl pkcs12 -in  certs_pack.pfx -nocerts -out elastic-privatekey.key

openssl rsa -in elastic-privatekey.key -out elastic-privatekey_decryp.key

openssl pkcs8 -inform PEM -outform PEM -in elastic-privatekey_decryp.key -topk8 -nocrypt -v1 PBE-SHA1-3DES -out elastic-privatekey.pem

# root
openssl x509 -in root.cer -outform PEM -out rootca.pem

```

# In case of logstash

```
openssl pkcs8 -topk8 -nocrypt -in logstash.key -out logstash.pem

```
