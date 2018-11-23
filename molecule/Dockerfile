FROM supertylerc/ansible:amd64
MAINTAINER "Tyler Christiansen <code@tylerc.me>"

ARG MOLECULE_VERSION=latest
USER root

RUN apk --no-cache add \
    gcc \
    musl-dev \
    python-dev \
    linux-headers \
  && [ "${MOLECULE_VERSION}" = "latest" ] \
    && pip install molecule docker \
    || pip install molecule=="${MOLECULE_VERSION}" docker \
  && apk del \
    gcc \
    python-dev \
    binutils \
    isl \
    libgomp \
    libatomic \
    pkgconf \
    mpfr3 \
    mpc1 \
    musl-dev \
    linux-headers

USER ansible

ENTRYPOINT ["molecule"]
