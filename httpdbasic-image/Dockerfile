FROM rhel7:latest

WORKDIR /home/

ADD http.repo /etc/yum.repos.d/
ADD soe.repo /etc/yum.repos.d/

RUN yum install -y httpd
RUN yum install -y wget iputils bind-utils net-tools

RUN yum update all; yum clean all;

ADD index.html /var/www/html/

CMD["/usr/sbin/httpd","-D","FOREGROUND"]
