FROM ubuntu:14.04

RUN apt-get update
RUN apt-get install -y apache2
RUN apt-get install -y zip
RUN apt-get install -y php5 libapache2-mod-php5
RUN apt-get install -y php5-mysql php5-curl php5-gd php5-idn php-pear php5-imagick php5-imap php5-mcrypt php5-memcache php5-ming php5-ps php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl
COPY conf/ /tmp/
COPY conf/conf /tmp/
COPY src/www.zip /var/www/html
COPY conf/start.sh /start.sh
RUN chmod +x /start.sh

WORKDIR /root/
RUN apt-get -y install -f
EXPOSE 80
CMD ["/start.sh"]
