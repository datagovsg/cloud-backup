FROM python:3.6

ARG ansible_version=2.5.1
ARG aws_cli_version=1.15.9

RUN set -xe \
    && apt-get update \
    && apt-get install -y unzip jq \
    && pip install "ansible==${ansible_version}" "awscli==${aws_cli_version}" \
    && ansible --version \
    && jq --version \
    && aws --version

WORKDIR /opt/nomad_backup
COPY *.yml ./
