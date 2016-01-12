#
# create container for travis-ci tool
#

from ubuntu:wily

RUN apt-get install build-essential ruby-dev ruby
RUN gem install travis


ENTRYPOINT ["/usr/local/bin/travis"]
