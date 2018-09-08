FROM mono:5.12

LABEL maintainer="daniel.lavoie@invivoo.com"

USER root

RUN groupadd -r xcomponent && useradd --no-log-init -r -g xcomponent xcomponent

RUN apt-get update && apt-get install -y unzip && \
  mkdir /home/xcomponent && \
  chown -R xcomponent:xcomponent /home/xcomponent && \
  chmod -R 700 /home/xcomponent

USER xcomponent

RUN mkdir -p /home/xcomponent && \
    curl -SL https://www.nuget.org/api/v2/package/XComponent.Runtime.Community/5.0.17 --output /home/xcomponent/xcomponent.zip && \
    unzip /home/xcomponent/xcomponent.zip -d /home/xcomponent && \
    rm /home/xcomponent/xcomponent.zip

WORKDIR /home/xcomponent/tools/XCRuntime