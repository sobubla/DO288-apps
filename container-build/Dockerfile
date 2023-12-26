# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

LABEL io.k8s.description="A basic Apache HTTP Server Child Omgae, uses ONBUILD" \
      io.k8s.display-name="Apache HTTP Server"  \
      io.openshift.expose-services="8080:http"  \
      io.opendhift.tags="apache, httpd"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf && \
    sed -i "s/#ServerName www.example.com/ServerName 0.0.0.0:8080/g" /etc/httpd/conf/httpd.conf && \
    chgrp -R 0 /var/log/httpd /var/run/httpd && \
    chmod -R g=u /var/log/httpd /var/run/httpd

EXPOSE 8080

USER 1001

