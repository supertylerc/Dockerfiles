FROM alpine:3.8             
MAINTAINER "Tyler Christiansen <code@tylerc.me>"
                                                  
ARG ANSIGENOME_VERSION=latest
              
RUN adduser -D ansible

RUN apk --no-cache add \
    py2-pip \
  && pip install --upgrade pip \ 
  && pip install \  
    requests \ 
  && [ "${ANSIGENOME_VERSION}" = "latest" ] \
     && \
       pip install ansigenome \
     || \
       pip install ansigenome=="${ANSIGENOME_VERSION}"

USER ansible

ENTRYPOINT ["ansigenome"]
