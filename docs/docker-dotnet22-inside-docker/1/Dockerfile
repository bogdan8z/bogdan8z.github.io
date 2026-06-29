FROM mcr.microsoft.com/dotnet/core/sdk:2.2-bionic

#****************     utilities     ****************************************************
RUN set -ex \
    && apt-get update \
    && apt-get install -y apt-transport-https software-properties-common ca-certificates curl wget


#****************     docker     *******************************************************
RUN set -ex \
    && wget https://download.docker.com/linux/ubuntu/gpg \
    && apt-key add gpg

RUN set -ex \
    && echo "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | tee /etc/apt/sources.list.d/docker.list \
    && apt-get update \
    && apt-cache policy docker-ce

RUN set -ex \
    && apt-get install -y docker-ce
