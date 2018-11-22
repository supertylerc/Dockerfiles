FROM supertylerc/ansible:amd64
MAINTAINER "Tyler Christiansen <code@tylerc.me>"

ARG ANSIBLE_LINT_VERSION=latest
USER root

RUN [ "${ANSIBLE_LINT_VERSION}" = "latest" ] \
    && \
      pip install ansible-lint \
    || \
      pip install ansible-lint=="${ANSIBLE_LINT_VERSION}"

USER ansible

ENTRYPOINT ["ansible-lint"]
