FROM alpine:3.8
MAINTAINER "Tyler Christiansen <code@tylerc.me>"

ARG RADON_VERSION=latest

RUN adduser -D radon

RUN apk --no-cache add \
    py3-pip \
  && pip3 install --upgrade pip \
  && pip3 install colorama \
  && [ "${RADON_VERSION}" = "latest" ] \
     && \
       pip3 install radon \
     || \
       pip3 install radon=="${RADON_VERSION}" \
  && rm -rf /usr/share/man/man1 \
  && rm -rf /usr/share/man/man7 \
  && rm -rf /tmp/*

VOLUME ["/code"]

USER radon
WORKDIR /code

ENTRYPOINT ["radon"]
