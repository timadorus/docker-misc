FROM ubuntu:wily

RUN apt-get update

RUN apt-get -y upgrade

RUN apt-get -y install octave

VOLUME ["/usr_data"]

WORKDIR /usr_data

ENTRYPOINT ["octave", "--no-gui", "-W"]
