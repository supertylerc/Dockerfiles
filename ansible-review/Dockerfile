FROM supertylerc/ansible:amd64
MAINTAINER "Tyler Christiansen <code@tylerc.me>"

ARG ANSIBLE_REVIEW_VERSION=latest
USER root

RUN [ "${ANSIBLE_REVIEW_VERSION}" = "latest" ] \
    && \
      pip install ansible-review \
    || \
      pip install ansible-review=="${ANSIBLE_REVIEW_VERSION}"

USER ansible

ENTRYPOINT ["ansible-review"]
