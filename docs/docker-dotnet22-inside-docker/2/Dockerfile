
FROM ubuntu:18.04

#****************     utilities     *******************************************************
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


#****************     .NET-CORE     *******************************************************
RUN set -ex \
    && wget -q https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb \
    && dpkg -i packages-microsoft-prod.deb \
    && apt-get update \
    && apt-get install -y apt-transport-https \
    && apt-get update \
    && apt-get install -y dotnet-sdk-2.1.200
    #2.1.815?
#****************     END .NET-CORE     *******************************************************
