# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.134.0/containers/python-3/.devcontainer/base.Dockerfile
ARG VARIANT="3.6"
FROM mcr.microsoft.com/vscode/devcontainers/python:0-${VARIANT}


# [Optional] If your pip requirements rarely change, uncomment this section to add them to the image.
COPY rasa/requirements.txt /tmp/pip-tmp/
RUN pip3 --disable-pip-version-check --no-cache-dir install -r /tmp/pip-tmp/requirements.txt \
    && rm -rf /tmp/pip-tmp 


USER root

RUN python3 -m spacy info
RUN python3 -m spacy download pl_core_news_lg
RUN python3 -m spacy link pl_core_news_lg pl

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update \
#     && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>