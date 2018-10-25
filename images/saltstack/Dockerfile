from ubuntu:16.04

RUN apt-get update -y --force-yes
RUN apt-get install net-tools -y

RUN apt-get install salt-master -y
RUN apt-get install salt-minion -y

RUN echo "master: $(ip route get 1| awk '{print $NF;exit}')" > /etc/salt/minion
RUN echo "id: minion" >> /etc/salt/minion

RUN salt-master -d
RUN salt-minion -d

## RUN apt install python-pip -y

COPY accept-keys.sh accept-keys.sh
RUN chmod 777 accept-keys.sh
#CMD ["/accept-keys.sh"]
