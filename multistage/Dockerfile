FROM centos:7 AS extract
RUN yum update -y && yum install unzip -y
ADD https://www.free-css.com/assets/files/free-css-templates/download/page293/dgital.zip .
RUN mkdir /opt/temp 
RUN unzip dgital.zip -d /opt/temp
RUN mv /opt/temp/* /opt/temp/dgital


FROM centos:7
RUN yum update -y && yum install httpd -y
WORKDIR /var/www/html
COPY --from=extract /opt/temp/dgital  /var/www/html/ 
EXPOSE 80/tcp
CMD ["httpd", "-D" , "FOREGROUND"]


