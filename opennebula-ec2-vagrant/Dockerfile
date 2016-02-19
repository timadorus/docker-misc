#
# Install a container with all the command line tools needed to deploy virtual machines
# to a private cloud running OpenNebula.
#
# Vagrant is supported via the EC2 API.
#

FROM ubuntu:wily

RUN apt-get -y install wget

RUN  wget -q -O- http://downloads.opennebula.org/repo/Ubuntu/repo.key | apt-key add -
RUN apt-get update

RUN echo "deb http://downloads.opennebula.org/repo/4.14/Ubuntu/14.04/ stable opennebula" > /etc/apt/sources.list.d/opennebula.list

RUN apt-get -y upgrade

# need sunstone for the 'econe' tools. Don't start or even configure the service
RUN apt-get -y install opennebula-tools opennebula-sunstone

# this will require manual input
RUN /usr/share/one/install_gems

# Install the debian version of vagrant. Currently there is no Ubuntu version
RUN wget https://releases.hashicorp.com/vagrant/1.8.1/vagrant_1.8.1_x86_64.deb
RUN dpkg -i vagrant_1.8.1_x86_64.deb
RUN vagrant plugin install vagrant-aws

VOLUME ["/usr_data"]

WORKDIR /usr_data

ENTRYPOINT ["octave", "--no-gui", "-W"]
