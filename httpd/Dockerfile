FROM httpd
MAINTAINER Stuart Winchester <swinches@redhat.com>

RUN sed -i 's|\(    CustomLog\).*|\1 /logs/access_log combined|' conf/httpd.conf
VOLUME /logs
