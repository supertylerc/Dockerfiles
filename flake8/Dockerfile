FROM alpine:3.8
MAINTAINER "Tyler Christiansen <code@tylerc.me>"

ARG FLAKE8_VERSION=latest

RUN adduser -D flake8

RUN apk --no-cache add \
    py2-pip \
  && pip install --upgrade pip \
  && [ "${FLAKE8_VERSION}" = "latest" ] \
     && \
       pip install flake8 \
     || \
       pip install flake8=="${flake8_VERSION}" \
  && rm -rf /usr/share/man/man1 \
  && rm -rf /usr/share/man/man7 \
  && rm -rf /tmp/*

VOLUME ["/code"]

USER flake8
WORKDIR /code

ENTRYPOINT ["flake8"]
