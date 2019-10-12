FROM ubuntu:16.04

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y ca-certificates openssh-server wget postfix

RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh && chmod 777 script.deb.sh && ./script.deb.sh && apt-get install -y gitlab-ce

RUN apt update && apt install -y tzdata && \
  apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 443 80 22

ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# docker build -t ex03 .
# docker run -it --rm -p 8080:80 -p 8022:22 -p 8443:443 --privileged ex03
# If you doesn't add something like tail -f /dev/null as the last command, your GitLab will shut down.
# And the last one tip. If you will see Whoops, GitLab is taking too much time to respond page,
# just wait and sometimes reload the page. It is absolutely normal. After 5-10 minutes you will get a ready Gitlab.