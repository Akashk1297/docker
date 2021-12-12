FROM local/c7-systemd
RUN yum -y install nginx; yum clean all; systemctl enable nginx.service
CMD ["/usr/sbin/init"]
