# shell-script-self-signed-ssl-certs
Shell Script To Create Self-Signed Certificate
If you want to create self-signed certificates quite often, you can make use of the following shell script. You just need to execute the script with the domain name or IP that you want to add to the certificate.

Save the following shell script as ssl.sh

Set the script executable permission by executing the following command.\
$chmod +x ssl.sh

Execute the script with the domain name or IP. For example,\
$./ssl.sh www.prateekdalal.com

/
/
**Note**: if you using git bash in window to generate .cert and .key , then you need to add like:\

Currently in script :\
openssl req -x509 \
            -sha256 -days 356 \
            -nodes \
            -newkey rsa:2048 \
            -subj "/CN=${DOMAIN}/C=US/L=San Fransisco" \
            -keyout rootCA.key -out rootCA.crt
            
            
After change in script:\
openssl req -x509 \
            -sha256 -days 356 \
            -nodes \
            -newkey rsa:2048 \
            -subj "//CN=${DOMAIN}//C=US//L=San Fransisco" \
            -keyout rootCA.key -out rootCA.crt
