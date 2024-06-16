FROM ubuntu:22.04 

RUN apt-get update && apt-get install -y nginx zip curl

# Corrected the path for nginx.conf and combined RUN commands to reduce layers
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

# Fixed the curl command and corrected the GitHub URL
RUN curl -o /var/www/html/master.zip -L https://github.com/gabrielecirulli/2048/archive/master.zip

# Added the missing space after 'cd' and corrected the folder name after unzipping
RUN cd /var/www/html && unzip master.zip && mv 2048-master/* . && rm -rf 2048-master master.zip 

EXPOSE 80

# Corrected the spelling of nginx in CMD
CMD ["/usr/sbin/nginx", "-c", "/etc/nginx/nginx.conf"]
