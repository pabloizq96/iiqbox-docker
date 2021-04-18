FROM bitnami/tomcat

#
# SETUP TIME ZONE
#
USER root
ENV TZ=Europe/Madrid
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

#
# Specify our exposed resources
#
EXPOSE 8080
EXPOSE 8000
EXPOSE 8001
USER 1001
