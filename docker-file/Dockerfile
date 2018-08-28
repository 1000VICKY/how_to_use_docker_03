FROM centos:latest

# 作成したユーザの情報
MAINTAINER 1000_VICKY <aki.sen.1209@gmail.com>

#RUN rpm -Uvh http://dev.mysql.com/get/mysql57-community-release-el7-7.noarch.rpm
#RUN yum -y install mysql-community-server mysql mysql-devel
RUN yum -y install epel-release
RUN rpm -Uvh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm
RUN yum -y install --enablerepo=remi,remi-php72 php php-devel php-mbstring php-pdo php-gd php-openssl php-mysql php-devel php-zlib which
RUN yum -y install httpd-devel httpd
RUN yum -y install supervisor
RUN yum -y remove mariadb-libs && rm -rf /var/lib/mysql
COPY supervisord.conf /etc/

EXPOSE 80

#CMD ["/usr/sbin/httpd", "-DFOREGROUND"]
#ENTRYPOINT ["/usr/sbin/httpd", "-DFOREGROUND"]
ENTRYPOINT ["supervisord"]
