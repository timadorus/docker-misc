#
# create container for travis-ci tool
#

from ubuntu:wily

RUN apt-get install build-essential ruby-dev ruby git
RUN gem install travis


ENTRYPOINT ["/usr/local/bin/travis"]
