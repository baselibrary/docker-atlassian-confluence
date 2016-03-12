FROM baselibrary/java:8
MAINTAINER ShawnMa <qsma@thoughtworks.com>

## Version
ENV CONFLUENCE_MAJOR   5
ENV CONFLUENCE_VERSION 5.9.6

## Packages
RUN \
  mkdir -p /opt/atlassian &&\
  curl -fsSL "http://www.atlassian.com/software/jira/downloads/binary/atlassian-confluence-${CONFLUENCE_VERSION}.tar.gz"| tar -zxvf - --strip-components=1 -C /opt/atlassian

## Configurations
RUN \
  mkdir -p /var/lib/atlassian &&\
  echo "confluence.home=/var/lib/atlassian" > "/opt/atlassian/confluence/WEB-INF/classes/confluence-init.properties"

EXPOSE 8090

WORKDIR /var/lib/confluence

VOLUME ["/var/lib/confluence"]

CMD ["/opt/atlassian/bin/catalina.sh", "run"]
