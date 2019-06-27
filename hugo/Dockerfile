FROM alpine:latest

RUN apk --update --no-cache add tar && rm -rf /var/cache/apk/*

ENV HUGO_BASE_URL http://localhost:1313
ENV HUGO_VERSION 0.55.6
ENV HUGO_BINARY hugo_${HUGO_VERSION}_Linux-64bit.tar.gz

ADD https://github.com/spf13/hugo/releases/download/v${HUGO_VERSION}/${HUGO_BINARY} /tmp/hugo.tar.gz

RUN tar -zxf /tmp/hugo.tar.gz -C /bin hugo && rm /tmp/hugo.tar.gz \
    && mkdir /usr/share/blog

WORKDIR /usr/share/blog
EXPOSE 1313
CMD hugo server -b ${HUGO_BASE_URL} --bind=0.0.0.0
