{% if cookiecutter.use_nvidia_docker == 'yes' -%}
FROM nvidia/cuda:8.0-cudnn5-devel-ubuntu16.04
{% else %}
FROM ubuntu:16.04
{%- endif %}

RUN apt-get update && apt-get install -y \
  git \
  python3.5 \
  python3-pip \
  python3-dev

RUN pip3 install --upgrade pip

COPY ./requirements.txt /requirements.txt
RUN pip install -r /requirements.txt

RUN useradd docker -u 1000 -s /bin/bash -m
USER docker

WORKDIR /work

ENTRYPOINT ["/bin/bash"]
