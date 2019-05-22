FROM python:3.6

ARG ansible_version=2.5.1
ARG aws_cli_version=1.15.9
ARG consul_version=1.0.7

RUN set -xe \
    && apt-get update \
    && apt-get install -y unzip \
    && pip install "ansible==${ansible_version}" "awscli==${aws_cli_version}" \
    && curl -Lo /tmp/consul.zip "https://releases.hashicorp.com/consul/${consul_version}/consul_${consul_version}_linux_amd64.zip" \
    && unzip -d /usr/local/bin /tmp/consul.zip \
    && rm /tmp/consul.zip \
    && ansible --version \
    && consul version \
    && aws --version

WORKDIR /opt/consul_backup
COPY site.yml ./
