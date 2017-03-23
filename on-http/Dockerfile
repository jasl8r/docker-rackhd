FROM rackhd/on-http:2.0.0
MAINTAINER jasl8r@alum.wpi.edu

ENV DOCKERIZE_VERSION=0.3.0

RUN curl -LO http://github.com/jwilder/dockerize/releases/download/v${DOCKERIZE_VERSION}/dockerize-linux-amd64-v${DOCKERIZE_VERSION}.tar.gz \
 && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-v${DOCKERIZE_VERSION}.tar.gz \
 && rm dockerize-linux-amd64-v${DOCKERIZE_VERSION}.tar.gz

COPY index.html /RackHD/on-http/static/http/
COPY config.json.tmpl /RackHD/

CMD ["dockerize", \
     "-template", "/RackHD/config.json.tmpl:/opt/monorail/config.json", \
     "node", "/RackHD/on-http/index.js" ]
