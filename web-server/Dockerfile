#FROM ubuntu
#RUN apt-get update
#RUN apt-get install apache2 -y
#EXPOSE 80/tcp
#CMD ["apachectl", "-D", "FOREGROUND"]

FROM centos:7
RUN yum install httpd -y
RUN echo "hello world " > /var/www/html/index.html
EXPOSE 80/tcp
CMD ["httpd", "-D" , "FOREGROUND"]
