FROM debian
RUN apt-get update && \
	apt-get upgrade -y && \
	apt-get install -y build-essential git vim && \
CMD bin/bash

# Create debianlike minimal working environment for C language =)
# Inside of folder 'docker build -t deb .'
# 'docker run --rm -ti deb'