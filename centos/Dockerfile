FROM centos:6

ENV RUBY_VERSION 2.3.1

RUN yum -y update && \
    yum install -y git gcc openssl-devel readline-devel zlib-devel && \
    yum clean all && \
    git clone https://github.com/rbenv/ruby-build.git && \
    ruby-build/install.sh && \
    /usr/local/bin/ruby-build $RUBY_VERSION /opt/ruby

ENV PATH /opt/ruby/bin:$PATH

RUN gem install itamae rake serverspec --no-ri --no-rdoc

CMD [ "irb" ]
