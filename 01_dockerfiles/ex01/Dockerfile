FROM debian
RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y wget bzip2 && \
    wget http://dl.4players.de/ts/releases/3.8.0/teamspeak3-server_linux_amd64-3.8.0.tar.bz2 && \
    tar -xvf teamspeak3-server_linux_amd64-3.8.0.tar.bz2
ENV TS3SERVER_LICENSE=accept
WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

# Inside of folder 'docker build -t ex01 .'
# 'docker run --rm -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01'