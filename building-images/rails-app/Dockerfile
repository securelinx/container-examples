# start with opensuse base
FROM opensuse/leap:15.2

# install ruby and any build dependencies
RUN zypper -n up && \
  zypper -n in \
    ruby2.5-rubygem-bundler \
    ruby-devel \
    libxslt1 \
    timezone \
    zlib-devel \
    sqlite3 sqlite3-devel \
    git \
    gzip \
    tar \
    libxml2-devel \
    make \
    gcc gcc-c++ && \
  zypper cc -a

# set environment
ARG APPDIR=/opt/rails/
ENV RAILS_ENV=test

# pull sample app from github
ADD https://api.github.com/repos/Azure-Samples/rubyrails-tasks/compare/master...HEAD /dev/null
RUN git clone https://github.com/Azure-Samples/rubyrails-tasks.git ${APPDIR}

# patch database settings for sample app
COPY patch $APPDIR

# Perform final config steps
WORKDIR $APPDIR
RUN chmod 775 bin/* && \
  bundle install && \
  bundle exec rake db:migrate

# use port 3000
EXPOSE 3000

CMD ["./bin/rails", "server"]
