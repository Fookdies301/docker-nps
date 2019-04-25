FROM alpine:3.9

WORKDIR /
ENV NPS_VERSION 0.23.0

RUN set -x && \
	wget --no-check-certificate https://github.com/cnlh/nps/releases/download/v${NPS_VERSION}/linux_amd64_client.tar.gz && \ 
	mkdir /usr/local/nps-client && \
	tar xzvf linux_amd64_client.tar.gz -C /usr/local/nps-client && \
	rm -rf /linux_amd64_client.tar.gz

WORKDIR /usr/local/nps-client
ADD start.sh /usr/local/nps-client/start.sh
RUN chmod +x /usr/local/nps-client/start.sh
ADD npc.conf /usr/local/nps-client/npc.conf
CMD /usr/local/nps-client/start.sh