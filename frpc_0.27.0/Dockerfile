FROM arm32v7/ubuntu:18.04
VOLUME ["/frpc/config"]
ENV FRP_VERSION 0.27.0
ENV FRP_URL https://github.com/fatedier/frp/releases/download/v${FRP_VERSION}/frp_${FRP_VERSION}_linux_arm.tar.gz

RUN apt-get update && \
apt-get install wget -y && \
wget ${FRP_URL} && \
mkdir frp_${FRP_VERSION} && \
mkdir -p /frpc/config && \
tar xvf frp_${FRP_VERSION}_linux_arm.tar.gz --strip-components 1 -C ./frp_${FRP_VERSION} && \
rm -rf frp_${FRP_VERSION}_linux_arm.tar.gz && \
echo '[common]   \n\                                                                                                                                                                                       
server_addr = 10.10.120.1      \n\                                                                                                                                                                  
server_port = 7000' > /frpc/config/frpc.ini && \
echo '#!/bin/bash \n\
/frp_${FRP_VERSION}/frpc -c /frpc/config/frpc.ini' > start.sh && \
chmod +x start.sh 

ENTRYPOINT [ "/start.sh" ]
